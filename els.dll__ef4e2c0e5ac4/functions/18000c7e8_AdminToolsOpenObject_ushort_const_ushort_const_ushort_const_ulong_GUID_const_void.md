# AdminToolsOpenObject(ushort const *,ushort const *,ushort const *,ulong,_GUID const &,void * *)

- ea: `0x18000c7e8`
- end: `0x18000c8b0`
- name: `?AdminToolsOpenObject@@YAJPEBG00KAEBU_GUID@@PEAPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d078`

## callees

- `0x1800033c0`
- `0x180003430`
- `0x18000c7e8`
- `0x18000ea30`

## import_xrefs

- `ACTIVEDS!__imp_ADsOpenObject` at `0x18000c8a9`

## pseudocode

```c
HRESULT __fastcall AdminToolsOpenObject(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        const struct _GUID *a5,
        void **a6)
{
  int v7; // edx
  DWORD v8; // r9d
  unsigned int v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = a4;
  if ( __TSS0__1__AdminToolsOpenObject__YAJPEBG00KAEBU_GUID__PEAPEAX_Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                         + (unsigned int)tls_index)
                                                                                       + 4LL) )
  {
    Init_thread_header(
      &__TSS0__1__AdminToolsOpenObject__YAJPEBG00KAEBU_GUID__PEAPEAX_Z_4HA,
      (unsigned int)tls_index,
      a3);
    if ( __TSS0__1__AdminToolsOpenObject__YAJPEBG00KAEBU_GUID__PEAPEAX_Z_4HA == -1 )
    {
      v10 = 0;
      if ( ReadAdminDebugRegkey(&v10) < 0 )
      {
        v7 = 192;
      }
      else
      {
        v7 = (((v10 & 1) == 0) << 6) | 0x80;
        if ( (v10 & 2) != 0 )
          v7 = ((v10 & 1) == 0) << 6;
      }
      `AdminToolsOpenObject'::`2'::additionalFlags = v7;
      Init_thread_footer(&__TSS0__1__AdminToolsOpenObject__YAJPEBG00KAEBU_GUID__PEAPEAX_Z_4HA);
    }
  }
  v8 = `AdminToolsOpenObject'::`2'::additionalFlags & 0xFFFFFF3E | 1;
  a5 = &IID_IDirectorySearch;
  if ( (`AdminToolsOpenObject'::`2'::additionalFlags & 2) == 0 )
    v8 = `AdminToolsOpenObject'::`2'::additionalFlags | 1;
  return ADsOpenObject(a1, 0, 0, v8, a5, a6);
}

```

## disassembly

```asm
0x18000c7e8  mov     [rsp+arg_18], r9d
0x18000c7ed  push    rbx
0x18000c7ee  sub     rsp, 30h
0x18000c7f2  mov     edx, cs:_tls_index
0x18000c7f8  mov     rbx, rcx
0x18000c7fb  mov     rax, gs:58h
0x18000c804  mov     ecx, 4
0x18000c809  mov     rax, [rax+rdx*8]
0x18000c80d  mov     eax, [rcx+rax]
0x18000c810  cmp     cs:?$TSS0@?1??AdminToolsOpenObject@@YAJPEBG00KAEBU_GUID@@PEAPEAX@Z@4HA, eax
0x18000c816  jle     short loc_18000C876
0x18000c818  lea     rcx, ?$TSS0@?1??AdminToolsOpenObject@@YAJPEBG00KAEBU_GUID@@PEAPEAX@Z@4HA
0x18000c81f  call    _Init_thread_header
0x18000c824  cmp     cs:?$TSS0@?1??AdminToolsOpenObject@@YAJPEBG00KAEBU_GUID@@PEAPEAX@Z@4HA, 0FFFFFFFFh
0x18000c82b  jnz     short loc_18000C876
0x18000c82d  lea     rcx, [rsp+38h+arg_18]; unsigned int *
0x18000c832  mov     [rsp+38h+arg_18], 0
0x18000c83a  call    ?ReadAdminDebugRegkey@@YAJPEAK@Z; ReadAdminDebugRegkey(ulong *)
0x18000c83f  test    eax, eax
0x18000c841  js      short loc_18000C85F
0x18000c843  mov     ecx, [rsp+38h+arg_18]
0x18000c847  not     ecx
0x18000c849  and     ecx, 1
0x18000c84c  shl     ecx, 6
0x18000c84f  mov     edx, ecx
0x18000c851  bts     edx, 7
0x18000c855  test    byte ptr [rsp+38h+arg_18], 2
0x18000c85a  cmovnz  edx, ecx
0x18000c85d  jmp     short loc_18000C864
0x18000c85f  mov     edx, 0C0h
0x18000c864  lea     rcx, ?$TSS0@?1??AdminToolsOpenObject@@YAJPEBG00KAEBU_GUID@@PEAPEAX@Z@4HA
0x18000c86b  mov     cs:?additionalFlags@?1??AdminToolsOpenObject@@YAJPEBG00KAEBU_GUID@@PEAPEAX@Z@4KA, edx; ulong `AdminToolsOpenObject(ushort const *,ushort const *,ushort const *,ulong,_GUID const &,void * *)'::`2'::additionalFlags
0x18000c871  call    _Init_thread_footer
0x18000c876  mov     ecx, cs:?additionalFlags@?1??AdminToolsOpenObject@@YAJPEBG00KAEBU_GUID@@PEAPEAX@Z@4KA; ulong `AdminToolsOpenObject(ushort const *,ushort const *,ushort const *,ulong,_GUID const &,void * *)'::`2'::additionalFlags
0x18000c87c  or      ecx, 1
0x18000c87f  mov     r9d, ecx
0x18000c882  and     r9d, 0FFFFFF3Fh
0x18000c889  lea     rax, IID_IDirectorySearch
0x18000c890  test    cl, 2
0x18000c893  mov     [rsp+38h+arg_20], rax
0x18000c898  cmovz   r9d, ecx
0x18000c89c  xor     r8d, r8d
0x18000c89f  xor     edx, edx
0x18000c8a1  mov     rcx, rbx
0x18000c8a4  add     rsp, 30h
0x18000c8a8  pop     rbx
0x18000c8a9  jmp     cs:__imp_ADsOpenObject
```
