# ReadFromFrameBuffer(CDDPDEV *,int,int,int,int)

- ea: `0x140001008`
- end: `0x1400011dc`
- name: `?ReadFromFrameBuffer@@YAXPEAUCDDPDEV@@HHHH@Z`
- size: `468`
- prototype: `void __fastcall(struct CDDPDEV *, int, int, int, int)`
- caller_count: `10`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002504`
- `0x140004904`
- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x14000919c`
- `0x1400161b0`
- `0x140019458`
- `0x140022e70`
- `0x1400235c0`

## callees

- `0x140001008`
- `0x140002470`
- `0x14000fbb4`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000107e`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000107e`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000109a`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140001102`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000109a`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140001102`
- `WIN32K!CddEngCombineRgn` at `0x14000112a`
- `WIN32K!CddEngCombineRgn` at `0x140001154`
- `WIN32K!CddEngCombineRgn` at `0x14000112a`
- `WIN32K!CddEngCombineRgn` at `0x140001154`
- `WIN32K!CddEngSetRectRgn` at `0x140001065`
- `WIN32K!CddEngSetRectRgn` at `0x140001065`
- `WIN32K!EngReleaseSemaphore` at `0x1400010bc`
- `WIN32K!EngReleaseSemaphore` at `0x1400010bc`
- `WIN32K!EngAcquireSemaphore` at `0x140001035`
- `WIN32K!EngAcquireSemaphore` at `0x140001035`

## pseudocode

```c
void __fastcall ReadFromFrameBuffer(struct CDDPDEV *a1, unsigned int a2, unsigned int a3, unsigned int a4, int a5)
{
  HSEMAPHORE v5; // rdi
  int v6; // r14d
  _QWORD *v11; // rsi
  unsigned int v12; // ebp
  int v13; // eax
  __int64 v14; // rdx
  int v15; // r8d
  int v16; // eax
  __int64 v17; // [rsp+30h] [rbp-48h] BYREF
  int v18; // [rsp+38h] [rbp-40h]

  v5 = (HSEMAPHORE)*((_QWORD *)a1 + 365);
  v6 = 0;
  if ( v5 )
  {
    EngAcquireSemaphore(*((HSEMAPHORE *)a1 + 365));
    v6 = 1;
  }
  v11 = (_QWORD *)((char *)a1 + 2824);
  if ( (unsigned int)CddEngSetRectRgn(*((_QWORD *)a1 + 353), a2, a3, a4, a5) )
  {
    v12 = 0;
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)a1 + 360));
    if ( *((_BYTE *)a1 + 2713) )
    {
      v12 = CddEngCombineRgn((char *)a1 + 2816, *((_QWORD *)a1 + 359), *v11, 1);
      if ( v12 > 1 )
      {
        v13 = CddEngCombineRgn((char *)a1 + 2824, *((_QWORD *)a1 + 359), *((_QWORD *)a1 + 352), 4);
        if ( v13 )
        {
          v14 = *((_QWORD *)a1 + 359);
          *((_QWORD *)a1 + 359) = *v11;
          *v11 = v14;
          if ( v13 == 1 )
            *((_BYTE *)a1 + 2713) = 0;
        }
      }
    }
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)a1 + 360));
    if ( v12 > 1 )
    {
      (*((void (**)(void))a1 + 74))();
      if ( !*((_BYTE *)a1 + 2718) && (++*((_DWORD *)a1 + 673) & *((_DWORD *)a1 + 674)) == 0 )
      {
        v16 = ~*((_DWORD *)a1 + 676);
        *((_BYTE *)a1 + 2718) = 1;
        *((_DWORD *)a1 + 675) &= v16;
      }
      CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v17, *((struct CDDMUTEX **)a1 + 686), v15);
      CddIssueCommand(a1, 1);
      if ( v18 )
        ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v17);
    }
  }
  if ( v5 )
  {
    if ( v6 )
      EngReleaseSemaphore(v5);
  }
}

```

## disassembly

```asm
0x140001008  push    rbx
0x14000100a  push    rbp
0x14000100b  push    rsi
0x14000100c  push    rdi
0x14000100d  push    r12
0x14000100f  push    r14
0x140001011  push    r15
0x140001013  sub     rsp, 40h
0x140001017  mov     rdi, [rcx+0B68h]
0x14000101e  xor     r14d, r14d
0x140001021  mov     ebp, r9d
0x140001024  mov     r15d, r8d
0x140001027  mov     r12d, edx
0x14000102a  mov     rbx, rcx
0x14000102d  test    rdi, rdi
0x140001030  jz      short loc_140001047
0x140001032  mov     rcx, rdi; hsem
0x140001035  call    cs:__imp_EngAcquireSemaphore
0x14000103c  nop     dword ptr [rax+rax+00h]
0x140001041  mov     r14d, 1
0x140001047  mov     eax, [rsp+78h+arg_20]
0x14000104e  lea     rsi, [rbx+0B08h]
0x140001055  mov     rcx, [rsi]
0x140001058  mov     r9d, ebp
0x14000105b  mov     r8d, r15d
0x14000105e  mov     [rsp+78h+var_58], eax
0x140001062  mov     edx, r12d
0x140001065  call    cs:__imp_CddEngSetRectRgn
0x14000106c  nop     dword ptr [rax+rax+00h]
0x140001071  test    eax, eax
0x140001073  jz      short loc_1400010AF
0x140001075  mov     rcx, [rbx+0B40h]
0x14000107c  xor     ebp, ebp
0x14000107e  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x140001085  nop     dword ptr [rax+rax+00h]
0x14000108a  cmp     [rbx+0A99h], bpl
0x140001091  jnz     short loc_140001110
0x140001093  mov     rcx, [rbx+0B40h]
0x14000109a  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x1400010a1  nop     dword ptr [rax+rax+00h]
0x1400010a6  cmp     ebp, 1
0x1400010a9  ja      loc_140001191
0x1400010af  test    rdi, rdi
0x1400010b2  jz      short loc_1400010C8
0x1400010b4  test    r14d, r14d
0x1400010b7  jz      short loc_1400010C8
0x1400010b9  mov     rcx, rdi; hsem
0x1400010bc  call    cs:__imp_EngReleaseSemaphore
0x1400010c3  nop     dword ptr [rax+rax+00h]
0x1400010c8  add     rsp, 40h
0x1400010cc  pop     r15
0x1400010ce  pop     r14
0x1400010d0  pop     r12
0x1400010d2  pop     rdi
0x1400010d3  pop     rsi
0x1400010d4  pop     rbp
0x1400010d5  pop     rbx
0x1400010d6  retn
0x1400010d8  mov     rdx, [rbx+1570h]; struct CDDMUTEX *
0x1400010df  lea     rcx, [rsp+78h+var_48]; this
0x1400010e4  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x1400010e9  mov     edx, 1
0x1400010ee  mov     rcx, rbx
0x1400010f1  call    ?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z; CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)
0x1400010f6  cmp     [rsp+78h+var_40], 0
0x1400010fb  jz      short loc_1400010AF
0x1400010fd  mov     rcx, [rsp+78h+var_48]
0x140001102  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140001109  nop     dword ptr [rax+rax+00h]
0x14000110e  jmp     short loc_1400010AF
0x140001110  mov     r8, [rsi]
0x140001113  lea     r15, [rbx+0B00h]
0x14000111a  mov     rdx, [rbx+0B38h]
0x140001121  mov     rcx, r15
0x140001124  mov     r9d, 1
0x14000112a  call    cs:__imp_CddEngCombineRgn
0x140001131  nop     dword ptr [rax+rax+00h]
0x140001136  mov     ebp, eax
0x140001138  cmp     eax, 1
0x14000113b  jbe     loc_140001093
0x140001141  mov     r8, [r15]
0x140001144  mov     r9d, 4
0x14000114a  mov     rdx, [rbx+0B38h]
0x140001151  mov     rcx, rsi
0x140001154  call    cs:__imp_CddEngCombineRgn
0x14000115b  nop     dword ptr [rax+rax+00h]
0x140001160  test    eax, eax
0x140001162  jz      loc_140001093
0x140001168  mov     rdx, [rbx+0B38h]
0x14000116f  mov     rcx, [rsi]
0x140001172  mov     [rbx+0B38h], rcx
0x140001179  mov     [rsi], rdx
0x14000117c  cmp     eax, 1
0x14000117f  jnz     loc_140001093
0x140001185  mov     byte ptr [rbx+0A99h], 0
0x14000118c  jmp     loc_140001093
0x140001191  mov     rax, [rbx+250h]
0x140001198  call    _guard_dispatch_icall
0x14000119d  cmp     byte ptr [rbx+0A9Eh], 0
0x1400011a4  jnz     loc_1400010D8
0x1400011aa  inc     dword ptr [rbx+0A84h]
0x1400011b0  mov     ecx, [rbx+0A84h]
0x1400011b6  test    [rbx+0A88h], ecx
0x1400011bc  jnz     loc_1400010D8
0x1400011c2  mov     eax, [rbx+0A90h]
0x1400011c8  not     eax
0x1400011ca  mov     byte ptr [rbx+0A9Eh], 1
0x1400011d1  and     [rbx+0A8Ch], eax
0x1400011d7  jmp     loc_1400010D8
```
