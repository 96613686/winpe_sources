# WriteDumpData(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *,_EXCEPTION_INFO * const,_MINIDUMP_USER_STREAM * const,ulong,_LIST_ENTRY * const)

- ea: `0x18000c19c`
- end: `0x18000c545`
- name: `?WriteDumpData@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@QEAU_EXCEPTION_INFO@@QEAU_MINIDUMP_USER_STREAM@@KQEAU_LIST_ENTRY@@@Z`
- size: `937`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *, struct _INTERNAL_PROCESS *, struct _EXCEPTION_INFO *const, struct _MINIDUMP_USER_STREAM *const, unsigned int, struct _LIST_ENTRY *const)`
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x18000f8e8`

## callees

- `0x180001710`
- `0x18000bcbc`
- `0x18000bdf8`
- `0x18000c19c`
- `0x18000c54c`
- `0x18000c67c`
- `0x18000d228`
- `0x18000d608`
- `0x18000d6f4`
- `0x18000df34`
- `0x18000e11c`
- `0x18000e438`
- `0x18000e6cc`
- `0x18000e898`
- `0x18000ea58`
- `0x18000eb24`
- `0x18000ec70`
- `0x18000eefc`
- `0x18000efb4`
- `0x18000f180`
- `0x18000f2b8`
- `0x18001bfac`
- `0x18001c4a0`
- `0x18002c010`

## string_xrefs

- `0x18000c225`: `WriteHeader.GetCurrentTimeDate failed, 0x%08x`
- `0x18000c4d6`: `WriteMemoryCompressed failed.\n`

## pseudocode

```c
__int64 __fastcall WriteDumpData(
        struct _MINIDUMP_STATE *a1,
        struct _MINIDUMP_STREAM_INFO *a2,
        struct _INTERNAL_PROCESS *a3,
        struct _EXCEPTION_INFO *const a4,
        struct _MINIDUMP_USER_STREAM *const a5,
        unsigned int a6,
        struct _LIST_ENTRY *const a7)
{
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // r15d
  __int64 result; // rax
  unsigned int v16; // edx
  unsigned int v17; // edx
  void *v18; // r8
  struct _INTERNAL_PROCESS *v19; // r8
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v21; // r15
  unsigned int v22; // [rsp+30h] [rbp-48h] BYREF
  struct _MINIDUMP_USER_STREAM *v23; // [rsp+38h] [rbp-40h]
  _DWORD v24[5]; // [rsp+40h] [rbp-38h] BYREF
  int v25; // [rsp+54h] [rbp-24h] BYREF
  __int64 v26; // [rsp+58h] [rbp-20h]

  v23 = a5;
  v24[2] = *(_DWORD *)a2;
  v24[3] = *((_DWORD *)a2 + 3);
  v24[4] = *((_DWORD *)a1 + 44);
  v11 = *((unsigned int *)a1 + 14);
  v12 = *((_QWORD *)a1 + 2);
  v26 = v11;
  v25 = 0;
  v24[0] = 1347241037;
  v24[1] = -1600149613;
  v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 8LL))(v12, &v25);
  v14 = v13;
  if ( v13 )
  {
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      "WriteHeader.GetCurrentTimeDate failed, 0x%08x",
      v13);
    return v14;
  }
  v14 = WriteAtOffset(a1, *((_DWORD *)a2 + 1), v24, 0x20u);
  if ( v14 )
    return v14;
  result = WriteSystemInfo(a1, a2);
  if ( !(_DWORD)result )
  {
    result = WriteMiscInfo(a1, a2, a3);
    if ( !(_DWORD)result )
    {
      result = WriteException(a1, a2, a4);
      if ( !(_DWORD)result )
      {
        if ( (*((_DWORD *)a1 + 14) & 0x4000002) != 0 )
          goto LABEL_13;
        v16 = *((_DWORD *)a2 + 26);
        v22 = (unsigned int)(*((_DWORD *)a2 + 27) - 4) >> 4;
        result = WriteAtOffset(a1, v16, &v22, 4u);
        if ( !(_DWORD)result )
        {
          *((_DWORD *)a2 + 28) += 4;
          result = WriteMemoryBlocks(a1, a2, a3);
          if ( !(_DWORD)result
            || (_DWORD)result == 1
            && (v17 = *((_DWORD *)a2 + 26),
                v22 = (unsigned int)(*((_DWORD *)a2 + 27) - 4) >> 4,
                result = WriteAtOffset(a1, v17, &v22, 4u),
                !(_DWORD)result) )
          {
LABEL_13:
            result = WriteThreadList(a1, a2, a3);
            if ( !(_DWORD)result )
            {
              result = WriteThreadInfoList(a1, a2, a3);
              if ( !(_DWORD)result )
              {
                result = WriteModuleList(a1, a2, a3);
                if ( !(_DWORD)result )
                {
                  result = WriteUnloadedModuleList(a1, a2, a3);
                  if ( !(_DWORD)result )
                  {
                    result = WriteFunctionTableList(a1, a2, a3);
                    if ( !(_DWORD)result )
                    {
                      if ( (*((_DWORD *)a1 + 14) & 0x40000) == 0
                        || (result = WriteTokenInformation(a1, a2, a3), !(_DWORD)result) )
                      {
                        result = WriteSystemMemoryInformation(a1, a2);
                        if ( !(_DWORD)result )
                        {
                          result = WriteProcessVmCounters(a1, a2);
                          if ( !(_DWORD)result )
                          {
                            v18 = (void *)*((_QWORD *)a3 + 9149);
                            if ( !v18
                              || (result = WriteAtOffset(a1, *((_DWORD *)a2 + 55), v18, *((_DWORD *)a2 + 56)),
                                  !(_DWORD)result) )
                            {
                              result = WriteThreadNames(a1, a2, a3);
                              if ( !(_DWORD)result )
                              {
                                v22 = 0;
                                result = WriteUserStreams(a1, a2, &v22, v23, a6);
                                if ( !(_DWORD)result )
                                {
                                  Flink = a7->Flink;
                                  if ( a7->Flink == a7 )
                                  {
LABEL_29:
                                    if ( (*((_BYTE *)a1 + 56) & 4) == 0
                                      || (result = GenWriteHandleOperations(a1, a2), !(_DWORD)result)
                                      && (result = GenWriteHandleData(a1, a3, a2), !(_DWORD)result) )
                                    {
                                      if ( (*((_DWORD *)a1 + 14) & 0x800) == 0
                                        || (result = WriteMemoryInfo(a1, a2), !(_DWORD)result) )
                                      {
                                        if ( (*((_DWORD *)a1 + 14) & 0x4000000) != 0 )
                                        {
                                          v14 = WriteMemoryCompressed(a1, a2, v19);
                                          if ( v14 )
                                          {
                                            (*(void (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)a1 + 5)
                                                                                                  + 8LL))(
                                              *((_QWORD *)a1 + 5),
                                              4,
                                              "WriteMemoryCompressed failed.\n");
                                            return v14;
                                          }
                                        }
                                        else if ( (*((_BYTE *)a1 + 56) & 2) != 0 )
                                        {
                                          result = WriteFullMemory(a1, a2, a3);
                                          if ( (_DWORD)result )
                                            return result;
                                        }
                                        return WriteDirectoryTable(a1, a2, a3, v23, a6, a7);
                                      }
                                    }
                                  }
                                  else
                                  {
                                    while ( 1 )
                                    {
                                      v21 = Flink->Flink;
                                      result = WriteUserStreams(
                                                 a1,
                                                 a2,
                                                 &v22,
                                                 *(struct _MINIDUMP_USER_STREAM **)((char *)&Flink[-1].Flink->Flink + 4),
                                                 (unsigned int)Flink[-1].Flink->Flink);
                                      if ( (_DWORD)result )
                                        break;
                                      Flink = v21;
                                      if ( v21 == a7 )
                                        goto LABEL_29;
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c19c  push    rbp
0x18000c19e  push    rbx
0x18000c19f  push    rsi
0x18000c1a0  push    rdi
0x18000c1a1  push    r12
0x18000c1a3  push    r13
0x18000c1a5  push    r14
0x18000c1a7  push    r15
0x18000c1a9  mov     rbp, rsp
0x18000c1ac  sub     rsp, 78h
0x18000c1b0  mov     rax, cs:__security_cookie
0x18000c1b7  xor     rax, rsp
0x18000c1ba  mov     [rbp+var_18], rax
0x18000c1be  mov     rax, [rbp+arg_20]
0x18000c1c2  mov     rbx, rcx
0x18000c1c5  mov     r12, [rbp+arg_30]
0x18000c1c9  mov     rdi, rdx
0x18000c1cc  mov     [rbp+var_40], rax
0x18000c1d0  mov     r14, r9
0x18000c1d3  mov     eax, [rdx]
0x18000c1d5  mov     rsi, r8
0x18000c1d8  mov     [rbp+var_30], eax
0x18000c1db  mov     eax, [rdx+0Ch]
0x18000c1de  lea     rdx, [rbp+var_24]
0x18000c1e2  mov     [rbp+var_2C], eax
0x18000c1e5  mov     eax, [rcx+0B0h]
0x18000c1eb  mov     [rbp+var_28], eax
0x18000c1ee  mov     eax, [rcx+38h]
0x18000c1f1  mov     rcx, [rcx+10h]
0x18000c1f5  mov     [rbp+var_20], rax
0x18000c1f9  mov     [rbp+var_24], 0
0x18000c200  mov     [rbp+var_38], 504D444Dh
0x18000c207  mov     [rbp+var_34], 0A09FA793h
0x18000c20e  mov     rax, [rcx]
0x18000c211  mov     rax, [rax+8]
0x18000c215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c21a  mov     r15d, eax
0x18000c21d  test    eax, eax
0x18000c21f  jz      short loc_18000C242
0x18000c221  mov     rcx, [rbx+28h]
0x18000c225  lea     r8, aWriteheaderGet; "WriteHeader.GetCurrentTimeDate failed, "...
0x18000c22c  mov     r9d, r15d
0x18000c22f  mov     edx, 4
0x18000c234  mov     rax, [rcx]
0x18000c237  mov     rax, [rax+8]
0x18000c23b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c240  jmp     short loc_18000C25E
0x18000c242  mov     edx, [rdi+4]; unsigned int
0x18000c245  lea     r8, [rbp+var_38]; void *
0x18000c249  mov     r9d, 20h ; ' '; unsigned int
0x18000c24f  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c252  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000c257  mov     r15d, eax
0x18000c25a  test    eax, eax
0x18000c25c  jz      short loc_18000C266
0x18000c25e  mov     eax, r15d
0x18000c261  jmp     loc_18000C528
0x18000c266  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c269  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c26c  call    ?WriteSystemInfo@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@@Z; WriteSystemInfo(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *)
0x18000c271  test    eax, eax
0x18000c273  jnz     loc_18000C528
0x18000c279  mov     r8, rsi; struct _INTERNAL_PROCESS *
0x18000c27c  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c27f  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c282  call    ?WriteMiscInfo@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z; WriteMiscInfo(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)
0x18000c287  test    eax, eax
0x18000c289  jnz     loc_18000C528
0x18000c28f  mov     r8, r14; struct _EXCEPTION_INFO *
0x18000c292  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c295  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c298  call    ?WriteException@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@QEAU_EXCEPTION_INFO@@@Z; WriteException(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_EXCEPTION_INFO * const)
0x18000c29d  test    eax, eax
0x18000c29f  jnz     loc_18000C528
0x18000c2a5  test    dword ptr [rbx+38h], 4000002h
0x18000c2ac  lea     r14d, [rax+4]
0x18000c2b0  jnz     short loc_18000C31D
0x18000c2b2  mov     eax, [rdi+6Ch]
0x18000c2b5  lea     r8, [rbp+var_48]; void *
0x18000c2b9  mov     edx, [rdi+68h]; unsigned int
0x18000c2bc  sub     eax, r14d
0x18000c2bf  shr     eax, 4
0x18000c2c2  mov     r9d, r14d; unsigned int
0x18000c2c5  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c2c8  mov     [rbp+var_48], eax
0x18000c2cb  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000c2d0  test    eax, eax
0x18000c2d2  jnz     loc_18000C528
0x18000c2d8  add     [rdi+70h], r14d
0x18000c2dc  mov     r8, rsi; struct _INTERNAL_PROCESS *
0x18000c2df  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c2e2  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c2e5  call    ?WriteMemoryBlocks@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z; WriteMemoryBlocks(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)
0x18000c2ea  test    eax, eax
0x18000c2ec  jz      short loc_18000C31D
0x18000c2ee  cmp     eax, 1
0x18000c2f1  jnz     loc_18000C528
0x18000c2f7  mov     eax, [rdi+6Ch]
0x18000c2fa  lea     r8, [rbp+var_48]; void *
0x18000c2fe  mov     edx, [rdi+68h]; unsigned int
0x18000c301  sub     eax, r14d
0x18000c304  shr     eax, 4
0x18000c307  mov     r9d, r14d; unsigned int
0x18000c30a  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c30d  mov     [rbp+var_48], eax
0x18000c310  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000c315  test    eax, eax
0x18000c317  jnz     loc_18000C528
0x18000c31d  mov     r8, rsi; struct _INTERNAL_PROCESS *
0x18000c320  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c323  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c326  call    ?WriteThreadList@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z; WriteThreadList(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)
0x18000c32b  test    eax, eax
0x18000c32d  jnz     loc_18000C528
0x18000c333  mov     r8, rsi; struct _INTERNAL_PROCESS *
0x18000c336  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c339  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c33c  call    ?WriteThreadInfoList@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z; WriteThreadInfoList(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)
0x18000c341  test    eax, eax
0x18000c343  jnz     loc_18000C528
0x18000c349  mov     r8, rsi; struct _INTERNAL_PROCESS *
0x18000c34c  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c34f  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c352  call    ?WriteModuleList@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z; WriteModuleList(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)
0x18000c357  test    eax, eax
0x18000c359  jnz     loc_18000C528
0x18000c35f  mov     r8, rsi; struct _INTERNAL_PROCESS *
0x18000c362  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c365  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c368  call    ?WriteUnloadedModuleList@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z; WriteUnloadedModuleList(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)
0x18000c36d  test    eax, eax
0x18000c36f  jnz     loc_18000C528
0x18000c375  mov     r8, rsi; struct _INTERNAL_PROCESS *
0x18000c378  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c37b  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c37e  call    ?WriteFunctionTableList@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z; WriteFunctionTableList(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)
0x18000c383  test    eax, eax
0x18000c385  jnz     loc_18000C528
0x18000c38b  test    dword ptr [rbx+38h], 40000h
0x18000c392  jz      short loc_18000C3AA
0x18000c394  mov     r8, rsi; struct _INTERNAL_PROCESS *
0x18000c397  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c39a  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c39d  call    ?WriteTokenInformation@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z; WriteTokenInformation(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)
0x18000c3a2  test    eax, eax
0x18000c3a4  jnz     loc_18000C528
0x18000c3aa  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c3ad  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c3b0  call    ?WriteSystemMemoryInformation@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@@Z; WriteSystemMemoryInformation(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *)
0x18000c3b5  test    eax, eax
0x18000c3b7  jnz     loc_18000C528
0x18000c3bd  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c3c0  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c3c3  call    ?WriteProcessVmCounters@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@@Z; WriteProcessVmCounters(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *)
0x18000c3c8  test    eax, eax
0x18000c3ca  jnz     loc_18000C528
0x18000c3d0  mov     r8, [rsi+11DE8h]; void *
0x18000c3d7  test    r8, r8
0x18000c3da  jz      short loc_18000C3F9
0x18000c3dc  mov     r9d, [rdi+0E0h]; unsigned int
0x18000c3e3  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c3e6  mov     edx, [rdi+0DCh]; unsigned int
0x18000c3ec  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000c3f1  test    eax, eax
0x18000c3f3  jnz     loc_18000C528
0x18000c3f9  mov     r8, rsi; struct _INTERNAL_PROCESS *
0x18000c3fc  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c3ff  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c402  call    ?WriteThreadNames@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z; WriteThreadNames(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)
0x18000c407  test    eax, eax
0x18000c409  jnz     loc_18000C528
0x18000c40f  mov     r13d, [rbp+arg_28]
0x18000c413  lea     r8, [rbp+var_48]; unsigned int *
0x18000c417  mov     r9, [rbp+var_40]; struct _MINIDUMP_USER_STREAM *
0x18000c41b  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c41e  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c421  mov     [rsp+78h+var_58], r13d; unsigned int
0x18000c426  mov     [rbp+var_48], eax
0x18000c429  call    ?WriteUserStreams@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAKPEAU_MINIDUMP_USER_STREAM@@K@Z; WriteUserStreams(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,ulong *,_MINIDUMP_USER_STREAM *,ulong)
0x18000c42e  test    eax, eax
0x18000c430  jnz     loc_18000C528
0x18000c436  mov     rax, [r12]
0x18000c43a  cmp     rax, r12
0x18000c43d  jz      short loc_18000C470
0x18000c43f  mov     r9, [rax-10h]
0x18000c443  lea     r8, [rbp+var_48]; unsigned int *
0x18000c447  mov     r15, [rax]
0x18000c44a  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c44d  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c450  mov     eax, [r9]
0x18000c453  mov     r9, [r9+4]; struct _MINIDUMP_USER_STREAM *
0x18000c457  mov     [rsp+78h+var_58], eax; unsigned int
0x18000c45b  call    ?WriteUserStreams@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAKPEAU_MINIDUMP_USER_STREAM@@K@Z; WriteUserStreams(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,ulong *,_MINIDUMP_USER_STREAM *,ulong)
0x18000c460  test    eax, eax
0x18000c462  jnz     loc_18000C528
0x18000c468  mov     rax, r15
0x18000c46b  cmp     r15, r12
0x18000c46e  jnz     short loc_18000C43F
0x18000c470  test    [rbx+38h], r14b
0x18000c474  jz      short loc_18000C49F
0x18000c476  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c479  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c47c  call    ?GenWriteHandleOperations@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@@Z; GenWriteHandleOperations(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *)
0x18000c481  test    eax, eax
0x18000c483  jnz     loc_18000C528
0x18000c489  mov     r8, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c48c  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x18000c48f  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c492  call    ?GenWriteHandleData@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_MINIDUMP_STREAM_INFO@@@Z; GenWriteHandleData(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_MINIDUMP_STREAM_INFO *)
0x18000c497  test    eax, eax
0x18000c499  jnz     loc_18000C528
0x18000c49f  test    dword ptr [rbx+38h], 800h
0x18000c4a6  jz      short loc_18000C4B7
0x18000c4a8  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c4ab  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c4ae  call    ?WriteMemoryInfo@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@@Z; WriteMemoryInfo(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *)
0x18000c4b3  test    eax, eax
0x18000c4b5  jnz     short loc_18000C528
0x18000c4b7  test    dword ptr [rbx+38h], 4000000h
0x18000c4be  jz      short loc_18000C4F4
0x18000c4c0  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c4c3  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c4c6  call    ?WriteMemoryCompressed@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z; WriteMemoryCompressed(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)
0x18000c4cb  mov     r15d, eax
0x18000c4ce  test    eax, eax
0x18000c4d0  jz      short loc_18000C50C
0x18000c4d2  mov     r9, [rbx+28h]
0x18000c4d6  lea     r8, aWritememorycom_0; "WriteMemoryCompressed failed.\n"
0x18000c4dd  mov     edx, r14d
0x18000c4e0  mov     rcx, [r9]
0x18000c4e3  mov     rax, [rcx+8]
0x18000c4e7  mov     rcx, r9
0x18000c4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4ef  jmp     loc_18000C25E
0x18000c4f4  test    byte ptr [rbx+38h], 2
0x18000c4f8  jz      short loc_18000C50C
0x18000c4fa  mov     r8, rsi; struct _INTERNAL_PROCESS *
0x18000c4fd  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c500  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c503  call    ?WriteFullMemory@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z; WriteFullMemory(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)
0x18000c508  test    eax, eax
0x18000c50a  jnz     short loc_18000C528
0x18000c50c  mov     r9, [rbp+var_40]; struct _MINIDUMP_USER_STREAM *
0x18000c510  mov     r8, rsi; struct _INTERNAL_PROCESS *
0x18000c513  mov     [rsp+78h+var_50], r12; struct _LIST_ENTRY *
0x18000c518  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000c51b  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000c51e  mov     [rsp+78h+var_58], r13d; unsigned int
0x18000c523  call    ?WriteDirectoryTable@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@PEAU_MINIDUMP_USER_STREAM@@KPEAU_LIST_ENTRY@@@Z; WriteDirectoryTable(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *,_MINIDUMP_USER_STREAM *,ulong,_LIST_ENTRY *)
0x18000c528  mov     rcx, [rbp+var_18]
0x18000c52c  xor     rcx, rsp; StackCookie
0x18000c52f  call    __security_check_cookie
0x18000c534  add     rsp, 78h
0x18000c538  pop     r15
0x18000c53a  pop     r14
0x18000c53c  pop     r13
0x18000c53e  pop     r12
0x18000c540  pop     rdi
0x18000c541  pop     rsi
0x18000c542  pop     rbx
0x18000c543  pop     rbp
0x18000c544  retn
```
