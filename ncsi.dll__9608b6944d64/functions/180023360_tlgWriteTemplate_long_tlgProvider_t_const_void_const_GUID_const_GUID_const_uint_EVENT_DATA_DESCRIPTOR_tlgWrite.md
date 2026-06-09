# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x180023360`
- end: `0x180023454`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, const size_t **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18003ee84`
- `0x18005fc84`

## callees

- `0x180023360`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18002342a`
- `ntdll!EtwEventWriteTransfer` at `0x18002342a`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const size_t **a5)
{
  const size_t *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  _DWORD v9[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v10; // [rsp+40h] [rbp-40h]
  __int16 *v11; // [rsp+48h] [rbp-38h] BYREF
  int v12; // [rsp+50h] [rbp-30h]
  int v13; // [rsp+54h] [rbp-2Ch]
  unsigned __int8 *v14; // [rsp+58h] [rbp-28h]
  int v15; // [rsp+60h] [rbp-20h]
  int v16; // [rsp+64h] [rbp-1Ch]
  const size_t *v17; // [rsp+68h] [rbp-18h]
  int v18; // [rsp+70h] [rbp-10h]
  int v19; // [rsp+74h] [rbp-Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)v5 + v6) );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v5 = &pServiceName;
    v7 = 2;
  }
  v18 = v7;
  v9[0] = *a2 << 24;
  v9[1] = *(unsigned __int16 *)(a2 + 1);
  v10 = *(_QWORD *)(a2 + 3);
  v11 = off_18009A050;
  v17 = v5;
  v19 = 0;
  v12 = (unsigned __int16)*off_18009A050;
  v15 = *(unsigned __int16 *)(a2 + 11);
  v14 = a2 + 11;
  v13 = 2;
  v16 = 1;
  return EtwEventWriteTransfer(RegHandle, v9, 0, 0, 3, &v11);
}

```

## disassembly

```asm
0x180023360  push    rbp
0x180023362  mov     rbp, rsp
0x180023365  sub     rsp, 80h
0x18002336c  mov     rax, cs:__security_cookie
0x180023373  xor     rax, rsp
0x180023376  mov     [rbp+var_8], rax
0x18002337a  mov     rax, [rbp+arg_20]
0x18002337e  xor     r8d, r8d
0x180023381  mov     r9d, 2
0x180023387  mov     rcx, [rax]
0x18002338a  test    rcx, rcx
0x18002338d  jz      loc_180023445
0x180023393  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023397  inc     rax
0x18002339a  cmp     [rcx+rax*2], r8w
0x18002339f  jnz     short loc_180023397
0x1800233a1  lea     eax, ds:2[rax*2]
0x1800233a8  mov     [rbp+var_10], eax
0x1800233ab  movzx   eax, byte ptr [rdx]
0x1800233ae  shl     eax, 18h
0x1800233b1  mov     [rbp+var_48], eax
0x1800233b4  movzx   eax, word ptr [rdx+1]
0x1800233b8  mov     [rbp+var_44], eax
0x1800233bb  mov     rax, [rdx+3]
0x1800233bf  mov     [rbp+var_40], rax
0x1800233c3  mov     rax, cs:off_18009A050
0x1800233ca  mov     [rbp+var_38], rax
0x1800233ce  mov     [rbp+var_18], rcx
0x1800233d2  lea     rcx, [rdx+0Bh]
0x1800233d6  mov     [rbp+var_C], r8d
0x1800233da  lea     rdx, [rbp+var_48]
0x1800233de  movzx   eax, word ptr [rax]
0x1800233e1  mov     [rbp+var_30], eax
0x1800233e4  movzx   eax, word ptr [rcx]
0x1800233e7  mov     [rbp+var_20], eax
0x1800233ea  lea     rax, _TraceLoggingMetadataEnd
0x1800233f1  mov     [rbp+var_28], rcx
0x1800233f5  lea     rcx, _TraceLoggingMetadata
0x1800233fc  sub     eax, ecx
0x1800233fe  mov     [rbp+var_2C], r9d
0x180023402  mov     [rbp+var_1C], 1
0x180023409  xor     r9d, r9d
0x18002340c  mov     [rbp+var_50], eax
0x18002340f  mov     eax, [rbp+var_50]
0x180023412  mov     rcx, cs:RegHandle
0x180023419  lea     rax, [rbp+var_38]
0x18002341d  mov     [rsp+80h+var_58], rax
0x180023422  mov     [rsp+80h+var_60], 3
0x18002342a  call    cs:__imp_EtwEventWriteTransfer
0x180023430  mov     rcx, [rbp+var_8]
0x180023434  xor     rcx, rsp; StackCookie
0x180023437  call    __security_check_cookie
0x18002343c  add     rsp, 80h
0x180023443  pop     rbp
0x180023444  retn
0x180023445  lea     rcx, pServiceName
0x18002344c  mov     eax, r9d
0x18002344f  jmp     loc_1800233A8
```
