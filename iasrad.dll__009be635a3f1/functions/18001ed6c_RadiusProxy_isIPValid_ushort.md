# RadiusProxy::isIPValid(ushort *)

- ea: `0x18001ed6c`
- end: `0x18001f05f`
- name: `?isIPValid@RadiusProxy@@IEAA_NPEAG@Z`
- size: `755`
- prototype: `bool __fastcall(RadiusProxy *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001e6c4`

## callees

- `0x1800094e4`
- `0x18000a430`
- `0x18001d31c`
- `0x18001ed6c`
- `0x18001fc50`
- `0x18002e202`

## import_xrefs

- `msvcrt!free` at `0x18001f04a`
- `msvcrt!free` at `0x18001f04a`
- `msvcrt!malloc` at `0x18001ee0d`
- `msvcrt!malloc` at `0x18001ee0d`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18001ee94`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18001ee94`
- `IPHLPAPI!ParseNetworkString` at `0x18001edb5`
- `IPHLPAPI!ParseNetworkString` at `0x18001edb5`

## string_xrefs

- `0x18001ef88`: `RadiusProxy::isIPValid() IP %S provided through registry is set`
- `0x18001efdb`: `RadiusProxy::isIPValid() IP %S provided through registry is set`

## pseudocode

```c
char __fastcall RadiusProxy::isIPValid(RadiusProxy *this, unsigned __int16 *a2)
{
  char v3; // si
  IP_ADAPTER_ADDRESSES_LH *v4; // rdi
  int v5; // edx
  IP_ADAPTER_ADDRESSES_LH *v6; // rdx
  PIP_ADAPTER_UNICAST_ADDRESS_LH i; // rcx
  LPSOCKADDR lpSockaddr; // rax
  _BYTE v10[4]; // [rsp+30h] [rbp-238h] BYREF
  __int16 v11; // [rsp+34h] [rbp-234h]
  int v12; // [rsp+38h] [rbp-230h]
  __int64 v13; // [rsp+3Ch] [rbp-22Ch]
  __int64 v14; // [rsp+44h] [rbp-224h]
  ULONG Size; // [rsp+270h] [rbp+8h] BYREF
  int Size_4; // [rsp+274h] [rbp+Ch]

  Size_4 = HIDWORD(this);
  Size = 15000;
  memset_0(v10, 0, 0x210u);
  v3 = 0;
  if ( (unsigned int)ParseNetworkString(a2, 9, v10) )
  {
    v4 = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_41;
    }
    WppDbgPrint("RadiusProxy::isIPValid() IP %S is not in a valid IP, falling back to default IP");
    v5 = 11;
    goto LABEL_40;
  }
  v4 = (IP_ADAPTER_ADDRESSES_LH *)malloc(Size);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("RadiusProxy::isIPValid() Unable to allocate memory for pAdapterAddresses");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_71998f247ae0370d2143b01685e48c0c_Traceguids, "NPSRAD");
    }
    goto LABEL_41;
  }
  if ( GetAdaptersAddresses(0, 0x2Eu, 0, v4, &Size) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("RadiusProxy::isIPValid() GetAdaptersAddresses failed with error %d, dwSize %ld");
      WPP_SF_sdl(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
    goto LABEL_41;
  }
  v6 = v4;
LABEL_17:
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_41;
    }
    WppDbgPrint("RadiusProxy::isIPValid() No network adapter interface was found with IP %S, falling back to default IP");
    v5 = 16;
LABEL_40:
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)&WPP_71998f247ae0370d2143b01685e48c0c_Traceguids,
      (unsigned int)"NPSRAD",
      (__int64)a2);
    goto LABEL_41;
  }
  for ( i = v6->FirstUnicastAddress; ; i = i->Next )
  {
    if ( !i )
    {
      v6 = v6->Next;
      goto LABEL_17;
    }
    lpSockaddr = i->Address.lpSockaddr;
    if ( v11 != lpSockaddr->sa_family )
      continue;
    if ( v11 == 2 )
      break;
    if ( v11 == 23 && v14 == *(_QWORD *)&lpSockaddr[1].sa_family && v13 == *(_QWORD *)&lpSockaddr->sa_data[6] )
    {
      v3 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("RadiusProxy::isIPValid() IP %S provided through registry is set");
        v5 = 15;
        goto LABEL_40;
      }
      goto LABEL_41;
    }
LABEL_30:
    ;
  }
  if ( v12 != *(_DWORD *)&lpSockaddr->sa_data[2] )
    goto LABEL_30;
  v3 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("RadiusProxy::isIPValid() IP %S provided through registry is set");
    v5 = 14;
    goto LABEL_40;
  }
LABEL_41:
  free(v4);
  return v3;
}

```

## disassembly

```asm
0x18001ed6c  mov     rax, rsp
0x18001ed6f  mov     [rax+8], rcx
0x18001ed73  push    rbx
0x18001ed74  push    rbp
0x18001ed75  push    rsi
0x18001ed76  push    rdi
0x18001ed77  sub     rsp, 248h
0x18001ed7e  mov     rbp, rdx
0x18001ed81  mov     dword ptr [rax+8], 3A98h
0x18001ed88  xor     edx, edx; Val
0x18001ed8a  lea     rcx, [rsp+268h+var_238]; void *
0x18001ed8f  mov     r8d, 210h; Size
0x18001ed95  call    memset_0
0x18001ed9a  xor     r9d, r9d
0x18001ed9d  mov     [rsp+268h+SizePointer], 0
0x18001eda6  lea     r8, [rsp+268h+var_238]
0x18001edab  mov     rcx, rbp
0x18001edae  xor     sil, sil
0x18001edb1  lea     edx, [r9+9]
0x18001edb5  call    cs:__imp_ParseNetworkString
0x18001edbb  test    eax, eax
0x18001edbd  jz      short loc_18001EE06
0x18001edbf  xor     edi, edi
0x18001edc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edc8  lea     rax, WPP_GLOBAL_Control
0x18001edcf  cmp     rcx, rax
0x18001edd2  jz      loc_18001F047
0x18001edd8  cmp     byte ptr [rcx+19h], 3
0x18001eddc  jb      loc_18001F047
0x18001ede2  test    dword ptr [rcx+1Ch], 100h
0x18001ede9  jz      loc_18001F047
0x18001edef  mov     rdx, rbp
0x18001edf2  lea     rcx, aRadiusproxyIsi_2; "RadiusProxy::isIPValid() IP %S is not i"...
0x18001edf9  call    WppDbgPrint
0x18001edfe  lea     edx, [rdi+0Bh]
0x18001ee01  jmp     loc_18001F024
0x18001ee06  mov     ecx, dword ptr [rsp+268h+Size]; Size
0x18001ee0d  call    cs:__imp_malloc
0x18001ee13  mov     rdi, rax
0x18001ee16  test    rax, rax
0x18001ee19  jnz     short loc_18001EE7B
0x18001ee1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee22  lea     rax, WPP_GLOBAL_Control
0x18001ee29  cmp     rcx, rax
0x18001ee2c  jz      loc_18001F047
0x18001ee32  cmp     byte ptr [rcx+19h], 2
0x18001ee36  jb      loc_18001F047
0x18001ee3c  test    dword ptr [rcx+1Ch], 100h
0x18001ee43  jz      loc_18001F047
0x18001ee49  lea     rcx, aRadiusproxyIsi_3; "RadiusProxy::isIPValid() Unable to allo"...
0x18001ee50  call    WppDbgPrint
0x18001ee55  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee5c  lea     edx, [rdi+0Ch]
0x18001ee5f  lea     r9, aNpsrad; "NPSRAD"
0x18001ee66  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001ee6d  mov     rcx, [rcx+10h]
0x18001ee71  call    WPP_SF_s
0x18001ee76  jmp     loc_18001F047
0x18001ee7b  xor     r8d, r8d; Reserved
0x18001ee7e  lea     rax, [rsp+268h+Size]
0x18001ee86  mov     r9, rdi; AdapterAddresses
0x18001ee89  mov     [rsp+268h+SizePointer], rax; SizePointer
0x18001ee8e  xor     ecx, ecx; Family
0x18001ee90  lea     edx, [r8+2Eh]; Flags
0x18001ee94  call    cs:__imp_GetAdaptersAddresses
0x18001ee9a  mov     ebx, eax
0x18001ee9c  test    eax, eax
0x18001ee9e  jz      short loc_18001EF08
0x18001eea0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eea7  lea     rax, WPP_GLOBAL_Control
0x18001eeae  cmp     rcx, rax
0x18001eeb1  jz      loc_18001F047
0x18001eeb7  cmp     byte ptr [rcx+19h], 2
0x18001eebb  jb      loc_18001F047
0x18001eec1  test    dword ptr [rcx+1Ch], 100h
0x18001eec8  jz      loc_18001F047
0x18001eece  mov     r8d, dword ptr [rsp+268h+Size]
0x18001eed6  lea     rcx, aRadiusproxyIsi_0; "RadiusProxy::isIPValid() GetAdaptersAdd"...
0x18001eedd  mov     edx, ebx
0x18001eedf  call    WppDbgPrint
0x18001eee4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eeeb  mov     eax, dword ptr [rsp+268h+Size]
0x18001eef2  mov     [rsp+268h+var_240], eax
0x18001eef6  mov     dword ptr [rsp+268h+SizePointer], ebx
0x18001eefa  mov     rcx, [rcx+10h]
0x18001eefe  call    WPP_SF_sdl
0x18001ef03  jmp     loc_18001F047
0x18001ef08  mov     rbx, [rsp+268h+var_224]
0x18001ef0d  mov     rdx, rdi
0x18001ef10  mov     r10, [rsp+268h+var_22C]
0x18001ef15  mov     r11d, [rsp+268h+var_230]
0x18001ef1a  movzx   r9d, [rsp+268h+var_234]
0x18001ef20  test    rdx, rdx
0x18001ef23  jz      loc_18001EFEE
0x18001ef29  mov     rcx, [rdx+18h]
0x18001ef2d  test    rcx, rcx
0x18001ef30  jz      short loc_18001EFAA
0x18001ef32  mov     rax, [rcx+10h]
0x18001ef36  cmp     r9w, [rax]
0x18001ef3a  jnz     short loc_18001EFA4
0x18001ef3c  cmp     r9d, 2
0x18001ef40  jz      short loc_18001EF9E
0x18001ef42  cmp     r9d, 17h
0x18001ef46  jnz     short loc_18001EFA4
0x18001ef48  cmp     rbx, [rax+10h]
0x18001ef4c  jnz     short loc_18001EFA4
0x18001ef4e  cmp     r10, [rax+8]
0x18001ef52  jnz     short loc_18001EFA4
0x18001ef54  mov     sil, 1
0x18001ef57  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef5e  lea     rax, WPP_GLOBAL_Control
0x18001ef65  cmp     rcx, rax
0x18001ef68  jz      loc_18001F047
0x18001ef6e  cmp     byte ptr [rcx+19h], 4
0x18001ef72  jb      loc_18001F047
0x18001ef78  test    dword ptr [rcx+1Ch], 100h
0x18001ef7f  jz      loc_18001F047
0x18001ef85  mov     rdx, rbp
0x18001ef88  lea     rcx, aRadiusproxyIsi; "RadiusProxy::isIPValid() IP %S provided"...
0x18001ef8f  call    WppDbgPrint
0x18001ef94  mov     edx, 0Fh
0x18001ef99  jmp     loc_18001F024
0x18001ef9e  cmp     r11d, [rax+4]
0x18001efa2  jz      short loc_18001EFB3
0x18001efa4  mov     rcx, [rcx+8]
0x18001efa8  jmp     short loc_18001EF2D
0x18001efaa  mov     rdx, [rdx+8]
0x18001efae  jmp     loc_18001EF20
0x18001efb3  mov     sil, 1
0x18001efb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efbd  lea     rax, WPP_GLOBAL_Control
0x18001efc4  cmp     rcx, rax
0x18001efc7  jz      short loc_18001F047
0x18001efc9  cmp     byte ptr [rcx+19h], 4
0x18001efcd  jb      short loc_18001F047
0x18001efcf  test    dword ptr [rcx+1Ch], 100h
0x18001efd6  jz      short loc_18001F047
0x18001efd8  mov     rdx, rbp
0x18001efdb  lea     rcx, aRadiusproxyIsi; "RadiusProxy::isIPValid() IP %S provided"...
0x18001efe2  call    WppDbgPrint
0x18001efe7  mov     edx, 0Eh
0x18001efec  jmp     short loc_18001F024
0x18001efee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eff5  lea     rax, WPP_GLOBAL_Control
0x18001effc  cmp     rcx, rax
0x18001efff  jz      short loc_18001F047
0x18001f001  cmp     byte ptr [rcx+19h], 3
0x18001f005  jb      short loc_18001F047
0x18001f007  test    dword ptr [rcx+1Ch], 100h
0x18001f00e  jz      short loc_18001F047
0x18001f010  mov     rdx, rbp
0x18001f013  lea     rcx, aRadiusproxyIsi_1; "RadiusProxy::isIPValid() No network ada"...
0x18001f01a  call    WppDbgPrint
0x18001f01f  mov     edx, 10h
0x18001f024  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f02b  lea     r9, aNpsrad; "NPSRAD"
0x18001f032  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001f039  mov     [rsp+268h+SizePointer], rbp
0x18001f03e  mov     rcx, [rcx+10h]
0x18001f042  call    WPP_SF_sS
0x18001f047  mov     rcx, rdi; Block
0x18001f04a  call    cs:__imp_free
0x18001f050  mov     al, sil
0x18001f053  add     rsp, 248h
0x18001f05a  pop     rdi
0x18001f05b  pop     rsi
0x18001f05c  pop     rbp
0x18001f05d  pop     rbx
0x18001f05e  retn
```
