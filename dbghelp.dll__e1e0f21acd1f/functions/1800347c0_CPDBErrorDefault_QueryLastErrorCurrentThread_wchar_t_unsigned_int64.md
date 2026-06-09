# CPDBErrorDefault::QueryLastErrorCurrentThread(wchar_t *,unsigned __int64)

- ea: `0x1800347c0`
- end: `0x18003488a`
- name: `?QueryLastErrorCurrentThread@CPDBErrorDefault@@UEAAJPEA_W_K@Z`
- size: `202`
- prototype: `__int64 __fastcall(CPDBErrorDefault *__hidden this, wchar_t *, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800347c0`
- `0x1800362d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180034820`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180034820`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800347da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800347da`

## pseudocode

```c
__int64 __fastcall CPDBErrorDefault::QueryLastErrorCurrentThread(CPDBErrorDefault *this, wchar_t *a2, __int64 a3)
{
  DWORD CurrentThreadId; // eax
  DWORD v7; // esi
  __int64 result; // rax
  unsigned int v9; // ecx
  signed __int32 v10[8]; // [rsp+0h] [rbp-38h] BYREF
  unsigned int v11; // [rsp+40h] [rbp+8h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  v7 = CurrentThreadId;
  if ( a2 )
  {
    if ( (unsigned int)pdb_internal::Map<unsigned long,char *,pdb_internal::HashClass<unsigned long,6>,void,CriticalSectionNop>::find(
                         (char *)this + 144,
                         CurrentThreadId,
                         &v11) )
      _o_wcsncpy_s(a2, a3, *((_QWORD *)this + 22) + ((unsigned __int64)v11 << 11), -1);
    else
      *a2 = 0;
  }
  if ( (unsigned int)pdb_internal::Map<unsigned long,char *,pdb_internal::HashClass<unsigned long,6>,void,CriticalSectionNop>::find(
                       (char *)this + 32,
                       v7,
                       &v11) )
    return *(unsigned int *)(*((_QWORD *)this + 8) + 4LL * v11);
  if ( !*((_BYTE *)this + 24) )
    return 0;
  v9 = *((_DWORD *)this + 2);
  _InterlockedOr(v10, 0);
  result = 2;
  if ( v9 )
    return v9;
  return result;
}

```

## disassembly

```asm
0x1800347c0  push    rbx
0x1800347c2  push    rdi
0x1800347c3  sub     rsp, 28h
0x1800347c7  mov     [rsp+38h+arg_10], rsi
0x1800347cc  mov     rdi, rdx
0x1800347cf  mov     [rsp+38h+var_18], r14
0x1800347d4  mov     rbx, rcx
0x1800347d7  mov     r14, r8
0x1800347da  call    cs:__imp_GetCurrentThreadId
0x1800347e0  mov     esi, eax
0x1800347e2  test    rdi, rdi
0x1800347e5  jz      short loc_180034832
0x1800347e7  lea     r8, [rsp+38h+arg_0]
0x1800347ec  mov     [rsp+38h+arg_8], rbp
0x1800347f1  mov     edx, eax
0x1800347f3  lea     rcx, [rbx+90h]
0x1800347fa  call    ?find@?$Map@KPEADV?$HashClass@K$05@pdb_internal@@XVCriticalSectionNop@@@pdb_internal@@IEBAHKPEAI@Z; pdb_internal::Map<ulong,char *,pdb_internal::HashClass<ulong,6>,void,CriticalSectionNop>::find(ulong,uint *)
0x1800347ff  test    eax, eax
0x180034801  jz      short loc_180034828
0x180034803  mov     r8d, [rsp+38h+arg_0]
0x180034808  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18003480f  shl     r8, 0Bh
0x180034813  mov     rdx, r14
0x180034816  add     r8, [rbx+0B0h]
0x18003481d  mov     rcx, rdi
0x180034820  call    cs:__imp__o_wcsncpy_s
0x180034826  jmp     short loc_18003482D
0x180034828  xor     eax, eax
0x18003482a  mov     [rdi], ax
0x18003482d  mov     rbp, [rsp+38h+arg_8]
0x180034832  lea     r8, [rsp+38h+arg_0]
0x180034837  mov     edx, esi
0x180034839  lea     rcx, [rbx+20h]
0x18003483d  call    ?find@?$Map@KPEADV?$HashClass@K$05@pdb_internal@@XVCriticalSectionNop@@@pdb_internal@@IEBAHKPEAI@Z; pdb_internal::Map<ulong,char *,pdb_internal::HashClass<ulong,6>,void,CriticalSectionNop>::find(ulong,uint *)
0x180034842  mov     r14, [rsp+38h+var_18]
0x180034847  mov     rsi, [rsp+38h+arg_10]
0x18003484c  test    eax, eax
0x18003484e  jz      short loc_180034862
0x180034850  mov     ecx, [rsp+38h+arg_0]
0x180034854  mov     rax, [rbx+40h]
0x180034858  mov     eax, [rax+rcx*4]
0x18003485b  add     rsp, 28h
0x18003485f  pop     rdi
0x180034860  pop     rbx
0x180034861  retn
0x180034862  cmp     byte ptr [rbx+18h], 0
0x180034866  jz      short loc_180034881
0x180034868  mov     ecx, [rbx+8]
0x18003486b  lock or [rsp+38h+var_38], 0
0x180034870  test    ecx, ecx
0x180034872  mov     eax, 2
0x180034877  cmovnz  eax, ecx
0x18003487a  add     rsp, 28h
0x18003487e  pop     rdi
0x18003487f  pop     rbx
0x180034880  retn
0x180034881  xor     eax, eax
0x180034883  add     rsp, 28h
0x180034887  pop     rdi
0x180034888  pop     rbx
0x180034889  retn
```
