# TempSurfObjHelper::TempSurfObjHelper(CDDPDEV *,CddBitmap *)

- ea: `0x140015d40`
- end: `0x140015e0d`
- name: `??0TempSurfObjHelper@@QEAA@PEAUCDDPDEV@@PEAVCddBitmap@@@Z`
- size: `205`
- prototype: `TempSurfObjHelper *__fastcall(TempSurfObjHelper *__hidden this, struct CDDPDEV *, struct CddBitmap *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005cc0`
- `0x140007b00`

## callees

- `0x140015d40`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140015d6e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140015d6e`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140015d8b`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140015d8b`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140015dba`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140015dba`

## pseudocode

```c
TempSurfObjHelper *__fastcall TempSurfObjHelper::TempSurfObjHelper(
        TempSurfObjHelper *this,
        PVOID *a2,
        struct CddBitmap *a3)
{
  __int64 v6; // rbp
  _QWORD *v7; // rdx
  _QWORD *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rcx
  int v11; // eax

  *((_QWORD *)this + 1) = a2;
  KeWaitForSingleObject(a2[789], Executive, 0, 0, 0);
  v6 = *((_QWORD *)a2[688] + 363);
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v6);
  v7 = a2 + 787;
  v8 = a2[787];
  if ( (_QWORD *)v8[1] != v7 || (v9 = *v8, *(_QWORD **)(*v8 + 8LL) != v8) )
    __fastfail(3u);
  *v7 = v9;
  *(_QWORD *)(v9 + 8) = v7;
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v6);
  *(_QWORD *)this = v8;
  v10 = v8[2];
  *(_QWORD *)(v10 + 56) = 0;
  *(_QWORD *)(v10 + 48) = 0;
  *(_DWORD *)(v10 + 32) = *((_DWORD *)a3 + 4);
  *(_DWORD *)(v10 + 36) = *((_DWORD *)a3 + 5);
  v11 = 4 * *((_DWORD *)a3 + 4);
  *(_DWORD *)(v10 + 64) = v11;
  *(_DWORD *)(v10 + 40) = *((_DWORD *)a3 + 5) * v11;
  return this;
}

```

## disassembly

```asm
0x140015d40  push    rbx
0x140015d42  push    rbp
0x140015d43  push    rsi
0x140015d44  push    rdi
0x140015d45  sub     rsp, 38h
0x140015d49  mov     rbx, rdx
0x140015d4c  mov     [rcx+8], rdx
0x140015d50  mov     rdi, r8
0x140015d53  mov     [rsp+58h+Timeout], 0; Timeout
0x140015d5c  mov     rsi, rcx
0x140015d5f  xor     r9d, r9d; Alertable
0x140015d62  xor     r8d, r8d; WaitMode
0x140015d65  xor     edx, edx; WaitReason
0x140015d67  mov     rcx, [rbx+18A8h]; Object
0x140015d6e  call    cs:__imp_KeWaitForSingleObject
0x140015d75  nop     dword ptr [rax+rax+00h]
0x140015d7a  mov     rax, [rbx+1580h]
0x140015d81  mov     rbp, [rax+0B58h]
0x140015d88  mov     rcx, rbp
0x140015d8b  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x140015d92  nop     dword ptr [rax+rax+00h]
0x140015d97  lea     rdx, [rbx+1898h]
0x140015d9e  mov     rbx, [rdx]
0x140015da1  cmp     [rbx+8], rdx
0x140015da5  jnz     short loc_140015E06
0x140015da7  mov     rax, [rbx]
0x140015daa  cmp     [rax+8], rbx
0x140015dae  jnz     short loc_140015E06
0x140015db0  mov     [rdx], rax
0x140015db3  mov     rcx, rbp
0x140015db6  mov     [rax+8], rdx
0x140015dba  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140015dc1  nop     dword ptr [rax+rax+00h]
0x140015dc6  mov     [rsi], rbx
0x140015dc9  mov     rcx, [rbx+10h]
0x140015dcd  mov     qword ptr [rcx+38h], 0
0x140015dd5  mov     qword ptr [rcx+30h], 0
0x140015ddd  mov     eax, [rdi+10h]
0x140015de0  mov     [rcx+20h], eax
0x140015de3  mov     eax, [rdi+14h]
0x140015de6  mov     [rcx+24h], eax
0x140015de9  mov     eax, [rdi+10h]
0x140015dec  shl     eax, 2
0x140015def  mov     [rcx+40h], eax
0x140015df2  imul    eax, [rdi+14h]
0x140015df6  mov     [rcx+28h], eax
0x140015df9  mov     rax, rsi
0x140015dfc  add     rsp, 38h
0x140015e00  pop     rdi
0x140015e01  pop     rsi
0x140015e02  pop     rbp
0x140015e03  pop     rbx
0x140015e04  retn
0x140015e06  mov     ecx, 3
0x140015e0b  int     29h; Win8: RtlFailFast(ecx)
```
