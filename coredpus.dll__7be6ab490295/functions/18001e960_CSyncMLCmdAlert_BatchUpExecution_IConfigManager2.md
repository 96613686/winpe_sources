# CSyncMLCmdAlert::BatchUpExecution(IConfigManager2 *)

- ea: `0x18001e960`
- end: `0x18001eada`
- name: `?BatchUpExecution@CSyncMLCmdAlert@@UEAAJPEAUIConfigManager2@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(CSyncMLCmdAlert *__hidden this, struct IConfigManager2 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800034d0`
- `0x18000fad0`
- `0x18001650c`
- `0x18001e960`
- `0x180021624`
- `0x1800216cc`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdAlert::BatchUpExecution(
        const unsigned __int16 **this,
        struct IConfigManager2 *a2,
        __int64 a3,
        __int64 a4)
{
  signed int v5; // ebx
  const unsigned __int16 *v6; // rcx
  int v7; // ecx
  unsigned __int64 v8; // rcx
  unsigned int v10; // [rsp+48h] [rbp+10h] BYREF

  v10 = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    goto LABEL_29;
  }
  if ( *((_DWORD *)this[10] + 10) )
  {
    v5 = 0;
    CSyncMLCmd::SetBypassResult((CSyncMLCmd *)this);
    goto LABEL_31;
  }
  v5 = CSyncMLCmd::VerifyDTD((CSyncMLCmd *)this);
  if ( v5 < 0 )
    goto LABEL_29;
  v6 = this[21];
  if ( !v6 )
    goto LABEL_7;
  v5 = TToDword(v6, &v10);
  if ( v5 >= 0 )
  {
    a3 = 1;
    v7 = *((_DWORD *)this[9] + 9);
    if ( (unsigned int)(v7 + 2102722547) <= 1 )
    {
      if ( v10 != 1223 )
      {
        v5 = *((_DWORD *)this[9] + 9);
        if ( v7 >= 0 )
          goto LABEL_31;
        goto LABEL_29;
      }
LABEL_18:
      v5 = -2102722560;
      *((_DWORD *)this[10] + 7) = 1;
      goto LABEL_29;
    }
    switch ( v10 )
    {
      case 0x44Cu:
      case 0x44Du:
      case 0x44Eu:
      case 0x44Fu:
        v8 = ((char *)this[2] - (char *)this[1]) >> 3;
        if ( v8 )
        {
          if ( v10 == 1103 )
          {
            if ( v8 < 3 )
              break;
          }
          else if ( (char *)this[2] - (char *)this[1] != 16 )
          {
            break;
          }
          v5 = CSyncMLCmdAlert::ShowUI((CSyncMLCmdAlert *)this, v10);
          if ( v5 >= 0 )
            goto LABEL_31;
          goto LABEL_29;
        }
        break;
      case 0x4C6u:
        *((_DWORD *)this[10] + 111) |= 2u;
        goto LABEL_31;
      case 0x4C7u:
        if ( this[2] == this[1] )
          goto LABEL_18;
        break;
      default:
        v5 = -2147467263;
        goto LABEL_29;
    }
LABEL_7:
    v5 = -2102788095;
  }
LABEL_29:
  if ( *((int *)this + 15) >= 0 )
    *((_DWORD *)this + 15) = v5;
LABEL_31:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v10 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)&byte_1800372DF,
      a3,
      a4,
      (__int64)&v10);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001e960  mov     [rsp+arg_0], rbx
0x18001e965  push    rdi
0x18001e966  sub     rsp, 30h
0x18001e96a  mov     [rsp+38h+arg_8], 0
0x18001e972  mov     rdi, rcx
0x18001e975  test    rdx, rdx
0x18001e978  jnz     short loc_18001E984
0x18001e97a  mov     ebx, 80004003h
0x18001e97f  jmp     loc_18001EA97
0x18001e984  mov     rax, [rcx+50h]
0x18001e988  cmp     dword ptr [rax+28h], 0
0x18001e98c  jz      short loc_18001E99A
0x18001e98e  xor     ebx, ebx
0x18001e990  call    ?SetBypassResult@CSyncMLCmd@@QEAAXXZ; CSyncMLCmd::SetBypassResult(void)
0x18001e995  jmp     loc_18001EAA0
0x18001e99a  call    ?VerifyDTD@CSyncMLCmd@@IEBAJXZ; CSyncMLCmd::VerifyDTD(void)
0x18001e99f  mov     ebx, eax
0x18001e9a1  test    eax, eax
0x18001e9a3  js      loc_18001EA97
0x18001e9a9  mov     rcx, [rdi+0A8h]; unsigned __int16 *
0x18001e9b0  test    rcx, rcx
0x18001e9b3  jnz     short loc_18001E9BF
0x18001e9b5  mov     ebx, 82AA0001h
0x18001e9ba  jmp     loc_18001EA97
0x18001e9bf  lea     rdx, [rsp+38h+arg_8]; unsigned int *
0x18001e9c4  call    ?TToDword@@YAJPEBGPEAK@Z; TToDword(ushort const *,ulong *)
0x18001e9c9  mov     ebx, eax
0x18001e9cb  test    eax, eax
0x18001e9cd  js      loc_18001EA97
0x18001e9d3  mov     rax, [rdi+48h]
0x18001e9d7  mov     r8d, 1
0x18001e9dd  mov     ecx, [rax+24h]
0x18001e9e0  lea     eax, [rcx+7D54FFF3h]
0x18001e9e6  cmp     eax, r8d
0x18001e9e9  jbe     loc_18001EA87
0x18001e9ef  mov     edx, [rsp+38h+arg_8]; unsigned int
0x18001e9f3  mov     eax, edx
0x18001e9f5  sub     eax, 44Ch
0x18001e9fa  jz      short loc_18001EA42
0x18001e9fc  sub     eax, r8d
0x18001e9ff  jz      short loc_18001EA42
0x18001ea01  sub     eax, r8d
0x18001ea04  jz      short loc_18001EA42
0x18001ea06  sub     eax, r8d
0x18001ea09  jz      short loc_18001EA42
0x18001ea0b  sub     eax, 77h ; 'w'
0x18001ea0e  jz      short loc_18001EA35
0x18001ea10  cmp     eax, r8d
0x18001ea13  jz      short loc_18001EA1C
0x18001ea15  mov     ebx, 80004001h
0x18001ea1a  jmp     short loc_18001EA97
0x18001ea1c  mov     rax, [rdi+10h]
0x18001ea20  cmp     rax, [rdi+8]
0x18001ea24  jnz     short loc_18001E9B5
0x18001ea26  mov     rax, [rdi+50h]
0x18001ea2a  mov     ebx, 82AB0000h
0x18001ea2f  mov     [rax+1Ch], r8d
0x18001ea33  jmp     short loc_18001EA97
0x18001ea35  mov     rax, [rdi+50h]
0x18001ea39  or      dword ptr [rax+1BCh], 2
0x18001ea40  jmp     short loc_18001EAA0
0x18001ea42  mov     rax, [rdi+10h]
0x18001ea46  sub     rax, [rdi+8]
0x18001ea4a  mov     rcx, rax
0x18001ea4d  sar     rcx, 3
0x18001ea51  test    rcx, rcx
0x18001ea54  jz      loc_18001E9B5
0x18001ea5a  cmp     edx, 44Fh
0x18001ea60  jnz     short loc_18001EA6D
0x18001ea62  cmp     rcx, 3
0x18001ea66  jnb     short loc_18001EA77
0x18001ea68  jmp     loc_18001E9B5
0x18001ea6d  cmp     rax, 10h
0x18001ea71  jnz     loc_18001E9B5
0x18001ea77  mov     rcx, rdi; this
0x18001ea7a  call    ?ShowUI@CSyncMLCmdAlert@@AEAAJK@Z; CSyncMLCmdAlert::ShowUI(ulong)
0x18001ea7f  mov     ebx, eax
0x18001ea81  test    eax, eax
0x18001ea83  js      short loc_18001EA97
0x18001ea85  jmp     short loc_18001EAA0
0x18001ea87  cmp     [rsp+38h+arg_8], 4C7h
0x18001ea8f  jz      short loc_18001EA26
0x18001ea91  mov     ebx, ecx
0x18001ea93  test    ecx, ecx
0x18001ea95  jns     short loc_18001EAA0
0x18001ea97  cmp     dword ptr [rdi+3Ch], 0
0x18001ea9b  jl      short loc_18001EAA0
0x18001ea9d  mov     [rdi+3Ch], ebx
0x18001eaa0  mov     eax, cs:dword_18003E048
0x18001eaa6  cmp     eax, 5
0x18001eaa9  jbe     short loc_18001EACC
0x18001eaab  lea     rax, [rsp+38h+arg_8]
0x18001eab0  mov     [rsp+38h+arg_8], ebx
0x18001eab4  lea     rdx, byte_1800372DF
0x18001eabb  mov     [rsp+38h+var_18], rax
0x18001eac0  lea     rcx, dword_18003E048
0x18001eac7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001eacc  mov     eax, ebx
0x18001eace  mov     rbx, [rsp+38h+arg_0]
0x18001ead3  add     rsp, 30h
0x18001ead7  pop     rdi
0x18001ead8  retn
```
