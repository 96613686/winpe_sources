# DataStoreServer::LoadXMLResource(HINSTANCE__ *,ushort const *,ulong &,void * &)

- ea: `0x18000a19c`
- end: `0x18000a32e`
- name: `?LoadXMLResource@DataStoreServer@@AEAAKPEAUHINSTANCE__@@PEBGAEAKAEAPEAX@Z`
- size: `402`
- prototype: `unsigned int(DataStoreServer *__hidden this, HINSTANCE, const unsigned __int16 *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180008d7c`

## callees

- `0x1800020b1`
- `0x1800071ac`
- `0x18000a19c`
- `0x18000d990`

## import_xrefs

- `KERNEL32!FindResourceW` at `0x18000a1c1`
- `KERNEL32!FindResourceW` at `0x18000a1c1`
- `KERNEL32!GetLastError` at `0x18000a24f`
- `KERNEL32!GetLastError` at `0x18000a2ce`
- `KERNEL32!GetLastError` at `0x18000a24f`
- `KERNEL32!GetLastError` at `0x18000a2ce`
- `KERNEL32!SizeofResource` at `0x18000a1d9`
- `KERNEL32!SizeofResource` at `0x18000a1d9`
- `KERNEL32!LoadResource` at `0x18000a1f0`
- `KERNEL32!LoadResource` at `0x18000a1f0`
- `ole32!CoTaskMemAlloc` at `0x18000a200`
- `ole32!CoTaskMemAlloc` at `0x18000a200`

## string_xrefs

- `0x18000a2f7`: `DataStoreServer::LoadXMLResource() failed in FindResource():0x%x`
- `0x18000a2bd`: `DataStoreServer::LoadXMLResource() failed in LoadResource(): 0x%x, data size too small`
- `0x18000a284`: `DataStoreServer::LoadXMLResource() failed in LoadResource(): 0x%x`

## pseudocode

```c
__int64 __fastcall DataStoreServer::LoadXMLResource(
        DataStoreServer *this,
        HINSTANCE a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        void **a5)
{
  HRSRC ResourceW; // rax
  HRSRC v8; // rsi
  DWORD v9; // eax
  char *Resource; // rbp
  void *v11; // rax
  DWORD LastError; // ebx
  __int64 v13; // rdx

  *a4 = 0;
  ResourceW = FindResourceW(a2, a3, (LPCWSTR)0x17);
  v8 = ResourceW;
  if ( ResourceW )
  {
    v9 = SizeofResource(a2, ResourceW);
    *a4 = v9;
    if ( v9 <= 2 )
    {
      LastError = 13;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("DataStoreServer::LoadXMLResource() failed in LoadResource(): 0x%x, data size too small");
        v13 = 64;
        goto LABEL_19;
      }
    }
    else
    {
      Resource = (char *)LoadResource(a2, v8);
      if ( Resource )
      {
        v11 = CoTaskMemAlloc(*a4);
        *a5 = v11;
        if ( v11 )
        {
          LastError = 0;
          memcpy_0(v11, Resource + 2, *a4 - 2);
          *((_BYTE *)*a5 + *a4 - 2) = 0;
          *((_BYTE *)*a5 + *a4 - 1) = 0;
        }
        else
        {
          return 8;
        }
        return LastError;
      }
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("DataStoreServer::LoadXMLResource() failed in LoadResource(): 0x%x");
        v13 = 65;
LABEL_19:
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreServer::LoadXMLResource() failed in FindResource():0x%x");
      v13 = 63;
      goto LABEL_19;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18000a19c  push    rbx
0x18000a19e  push    rbp
0x18000a19f  push    rsi
0x18000a1a0  push    rdi
0x18000a1a1  sub     rsp, 38h
0x18000a1a5  mov     rax, r8
0x18000a1a8  mov     dword ptr [r9], 0
0x18000a1af  mov     rbx, rdx
0x18000a1b2  mov     r8d, 17h; lpType
0x18000a1b8  mov     rdx, rax; lpName
0x18000a1bb  mov     rcx, rbx; hModule
0x18000a1be  mov     rdi, r9
0x18000a1c1  call    cs:__imp_FindResourceW
0x18000a1c7  mov     rsi, rax
0x18000a1ca  test    rax, rax
0x18000a1cd  jz      loc_18000A2CE
0x18000a1d3  mov     rdx, rax; hResInfo
0x18000a1d6  mov     rcx, rbx; hModule
0x18000a1d9  call    cs:__imp_SizeofResource
0x18000a1df  mov     [rdi], eax
0x18000a1e1  cmp     eax, 2
0x18000a1e4  jbe     loc_18000A297
0x18000a1ea  mov     rdx, rsi; hResInfo
0x18000a1ed  mov     rcx, rbx; hModule
0x18000a1f0  call    cs:__imp_LoadResource
0x18000a1f6  mov     rbp, rax
0x18000a1f9  test    rax, rax
0x18000a1fc  jz      short loc_18000A24F
0x18000a1fe  mov     ecx, [rdi]; cb
0x18000a200  call    cs:__imp_CoTaskMemAlloc
0x18000a206  mov     rsi, [rsp+58h+arg_20]
0x18000a20e  mov     [rsi], rax
0x18000a211  test    rax, rax
0x18000a214  jz      short loc_18000A245
0x18000a216  mov     r8d, [rdi]
0x18000a219  lea     rdx, [rbp+2]; Src
0x18000a21d  sub     r8d, 2; Size
0x18000a221  mov     rcx, rax; void *
0x18000a224  xor     ebx, ebx
0x18000a226  call    memcpy_0
0x18000a22b  mov     ecx, [rdi]
0x18000a22d  mov     rax, [rsi]
0x18000a230  sub     ecx, 2
0x18000a233  mov     [rcx+rax], bl
0x18000a236  mov     ecx, [rdi]
0x18000a238  mov     rax, [rsi]
0x18000a23b  dec     ecx
0x18000a23d  mov     [rcx+rax], bl
0x18000a240  jmp     loc_18000A323
0x18000a245  mov     ebx, 8
0x18000a24a  jmp     loc_18000A323
0x18000a24f  call    cs:__imp_GetLastError
0x18000a255  mov     ebx, eax
0x18000a257  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a25e  lea     rax, WPP_GLOBAL_Control
0x18000a265  cmp     rcx, rax
0x18000a268  jz      loc_18000A323
0x18000a26e  cmp     byte ptr [rcx+19h], 2
0x18000a272  jb      loc_18000A323
0x18000a278  test    byte ptr [rcx+1Ch], 10h
0x18000a27c  jz      loc_18000A323
0x18000a282  mov     edx, ebx
0x18000a284  lea     rcx, aDatastoreserve_9; "DataStoreServer::LoadXMLResource() fail"...
0x18000a28b  call    WppDbgPrint
0x18000a290  mov     edx, 41h ; 'A'
0x18000a295  jmp     short loc_18000A308
0x18000a297  mov     ebx, 0Dh
0x18000a29c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2a3  lea     rax, WPP_GLOBAL_Control
0x18000a2aa  cmp     rcx, rax
0x18000a2ad  jz      short loc_18000A323
0x18000a2af  cmp     byte ptr [rcx+19h], 2
0x18000a2b3  jb      short loc_18000A323
0x18000a2b5  test    byte ptr [rcx+1Ch], 10h
0x18000a2b9  jz      short loc_18000A323
0x18000a2bb  mov     edx, ebx
0x18000a2bd  lea     rcx, aDatastoreserve_23; "DataStoreServer::LoadXMLResource() fail"...
0x18000a2c4  call    WppDbgPrint
0x18000a2c9  lea     edx, [rbx+33h]
0x18000a2cc  jmp     short loc_18000A308
0x18000a2ce  call    cs:__imp_GetLastError
0x18000a2d4  mov     ebx, eax
0x18000a2d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2dd  lea     rax, WPP_GLOBAL_Control
0x18000a2e4  cmp     rcx, rax
0x18000a2e7  jz      short loc_18000A323
0x18000a2e9  cmp     byte ptr [rcx+19h], 2
0x18000a2ed  jb      short loc_18000A323
0x18000a2ef  test    byte ptr [rcx+1Ch], 10h
0x18000a2f3  jz      short loc_18000A323
0x18000a2f5  mov     edx, ebx
0x18000a2f7  lea     rcx, aDatastoreserve_7; "DataStoreServer::LoadXMLResource() fail"...
0x18000a2fe  call    WppDbgPrint
0x18000a303  mov     edx, 3Fh ; '?'
0x18000a308  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a30f  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000a316  mov     [rsp+58h+var_38], ebx
0x18000a31a  mov     rcx, [rcx+10h]
0x18000a31e  call    WPP_SF_sd
0x18000a323  mov     eax, ebx
0x18000a325  add     rsp, 38h
0x18000a329  pop     rdi
0x18000a32a  pop     rsi
0x18000a32b  pop     rbp
0x18000a32c  pop     rbx
0x18000a32d  retn
```
