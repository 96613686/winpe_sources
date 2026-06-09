# StructuredException::copyExceptionPointers(_EXCEPTION_POINTERS const *)

- ea: `0x1800164b4`
- end: `0x18001662f`
- name: `?copyExceptionPointers@StructuredException@@AEAAXPEBU_EXCEPTION_POINTERS@@@Z`
- size: `379`
- prototype: `void __fastcall(StructuredException *__hidden this, const struct _EXCEPTION_POINTERS *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800161dc`
- `0x1800163e0`

## callees

- `0x1800164b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800164dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800164dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800164f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800164f3`

## pseudocode

```c
void __fastcall StructuredException::copyExceptionPointers(
        StructuredException *this,
        const struct _EXCEPTION_POINTERS *a2)
{
  PEXCEPTION_RECORD ExceptionRecord; // rax
  __int64 v5; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v7; // rcx
  PEXCEPTION_RECORD v8; // rdx
  __int64 v9; // r8
  PCONTEXT ContextRecord; // rax
  __int64 v11; // rdx
  StructuredException *v12; // rcx
  __int128 v13; // xmm1
  __int128 v14; // xmm0

  ExceptionRecord = a2->ExceptionRecord;
  v5 = 0;
  while ( ExceptionRecord )
  {
    ExceptionRecord = ExceptionRecord->ExceptionRecord;
    ++v5;
  }
  ProcessHeap = GetProcessHeap();
  if ( ProcessHeap )
    *((_QWORD *)this + 156) = HeapAlloc(ProcessHeap, 0, 152 * v5);
  v7 = *((_QWORD *)this + 156);
  if ( v7 )
  {
    v8 = a2->ExceptionRecord;
    v9 = 0;
    while ( v8 )
    {
      *(_OWORD *)v7 = *(_OWORD *)&v8->ExceptionCode;
      *(_OWORD *)(v7 + 16) = *(_OWORD *)&v8->ExceptionAddress;
      *(_OWORD *)(v7 + 32) = *(_OWORD *)v8->ExceptionInformation;
      *(_OWORD *)(v7 + 48) = *(_OWORD *)&v8->ExceptionInformation[2];
      *(_OWORD *)(v7 + 64) = *(_OWORD *)&v8->ExceptionInformation[4];
      *(_OWORD *)(v7 + 80) = *(_OWORD *)&v8->ExceptionInformation[6];
      *(_OWORD *)(v7 + 96) = *(_OWORD *)&v8->ExceptionInformation[8];
      *(_OWORD *)(v7 + 112) = *(_OWORD *)&v8->ExceptionInformation[10];
      *(_OWORD *)(v7 + 128) = *(_OWORD *)&v8->ExceptionInformation[12];
      *(_QWORD *)(v7 + 144) = v8->ExceptionInformation[14];
      if ( v9 )
        *(_QWORD *)(v9 + 8) = v7;
      v8 = v8->ExceptionRecord;
      v9 = v7;
      v7 += 152;
    }
  }
  ContextRecord = a2->ContextRecord;
  v11 = 9;
  v12 = this;
  do
  {
    *(_OWORD *)v12 = *(_OWORD *)&ContextRecord->P1Home;
    *((_OWORD *)v12 + 1) = *(_OWORD *)&ContextRecord->P3Home;
    *((_OWORD *)v12 + 2) = *(_OWORD *)&ContextRecord->P5Home;
    *((_OWORD *)v12 + 3) = *(_OWORD *)&ContextRecord->ContextFlags;
    *((_OWORD *)v12 + 4) = *(_OWORD *)&ContextRecord->SegGs;
    *((_OWORD *)v12 + 5) = *(_OWORD *)&ContextRecord->Dr1;
    *((_OWORD *)v12 + 6) = *(_OWORD *)&ContextRecord->Dr3;
    v13 = *(_OWORD *)&ContextRecord->Dr7;
    ContextRecord = (PCONTEXT)((char *)ContextRecord + 128);
    *((_OWORD *)v12 + 7) = v13;
    v12 = (StructuredException *)((char *)v12 + 128);
    --v11;
  }
  while ( v11 );
  *(_OWORD *)v12 = *(_OWORD *)&ContextRecord->P1Home;
  *((_OWORD *)v12 + 1) = *(_OWORD *)&ContextRecord->P3Home;
  *((_OWORD *)v12 + 2) = *(_OWORD *)&ContextRecord->P5Home;
  *((_OWORD *)v12 + 3) = *(_OWORD *)&ContextRecord->ContextFlags;
  v14 = *(_OWORD *)&ContextRecord->SegGs;
  *((_QWORD *)this + 154) = *((_QWORD *)this + 156);
  *((_QWORD *)this + 155) = this;
  *((_OWORD *)v12 + 4) = v14;
}

```

## disassembly

```asm
0x1800164b4  mov     [rsp+arg_0], rbx
0x1800164b9  mov     [rsp+arg_8], rsi
0x1800164be  push    rdi
0x1800164bf  sub     rsp, 20h
0x1800164c3  mov     rax, [rdx]
0x1800164c6  mov     rsi, rdx
0x1800164c9  mov     rbx, rcx
0x1800164cc  xor     edi, edi
0x1800164ce  jmp     short loc_1800164D7
0x1800164d0  mov     rax, [rax+8]
0x1800164d4  inc     rdi
0x1800164d7  test    rax, rax
0x1800164da  jnz     short loc_1800164D0
0x1800164dc  call    cs:__imp_GetProcessHeap
0x1800164e2  test    rax, rax
0x1800164e5  jz      short loc_180016500
0x1800164e7  imul    r8, rdi, 98h; dwBytes
0x1800164ee  xor     edx, edx; dwFlags
0x1800164f0  mov     rcx, rax; hHeap
0x1800164f3  call    cs:__imp_HeapAlloc
0x1800164f9  mov     [rbx+4E0h], rax
0x180016500  mov     rcx, [rbx+4E0h]
0x180016507  test    rcx, rcx
0x18001650a  jz      short loc_18001658A
0x18001650c  mov     rdx, [rsi]
0x18001650f  xor     r8d, r8d
0x180016512  jmp     short loc_180016585
0x180016514  movups  xmm0, xmmword ptr [rdx]
0x180016517  movups  xmmword ptr [rcx], xmm0
0x18001651a  movups  xmm1, xmmword ptr [rdx+10h]
0x18001651e  movups  xmmword ptr [rcx+10h], xmm1
0x180016522  movups  xmm0, xmmword ptr [rdx+20h]
0x180016526  movups  xmmword ptr [rcx+20h], xmm0
0x18001652a  movups  xmm1, xmmword ptr [rdx+30h]
0x18001652e  movups  xmmword ptr [rcx+30h], xmm1
0x180016532  movups  xmm0, xmmword ptr [rdx+40h]
0x180016536  movups  xmmword ptr [rcx+40h], xmm0
0x18001653a  movups  xmm1, xmmword ptr [rdx+50h]
0x18001653e  movups  xmmword ptr [rcx+50h], xmm1
0x180016542  movups  xmm0, xmmword ptr [rdx+60h]
0x180016546  movups  xmmword ptr [rcx+60h], xmm0
0x18001654a  movups  xmm1, xmmword ptr [rdx+70h]
0x18001654e  movups  xmmword ptr [rcx+70h], xmm1
0x180016552  movups  xmm0, xmmword ptr [rdx+80h]
0x180016559  movups  xmmword ptr [rcx+80h], xmm0
0x180016560  mov     rax, [rdx+90h]
0x180016567  mov     [rcx+90h], rax
0x18001656e  test    r8, r8
0x180016571  jz      short loc_180016577
0x180016573  mov     [r8+8], rcx
0x180016577  mov     rdx, [rdx+8]
0x18001657b  mov     r8, rcx
0x18001657e  add     rcx, 98h
0x180016585  test    rdx, rdx
0x180016588  jnz     short loc_180016514
0x18001658a  mov     rax, [rsi+8]
0x18001658e  mov     edx, 9
0x180016593  mov     rcx, rbx
0x180016596  lea     r8d, [rdx+77h]
0x18001659a  movups  xmm0, xmmword ptr [rax]
0x18001659d  movups  xmmword ptr [rcx], xmm0
0x1800165a0  movups  xmm1, xmmword ptr [rax+10h]
0x1800165a4  movups  xmmword ptr [rcx+10h], xmm1
0x1800165a8  movups  xmm0, xmmword ptr [rax+20h]
0x1800165ac  movups  xmmword ptr [rcx+20h], xmm0
0x1800165b0  movups  xmm1, xmmword ptr [rax+30h]
0x1800165b4  movups  xmmword ptr [rcx+30h], xmm1
0x1800165b8  movups  xmm0, xmmword ptr [rax+40h]
0x1800165bc  movups  xmmword ptr [rcx+40h], xmm0
0x1800165c0  movups  xmm1, xmmword ptr [rax+50h]
0x1800165c4  movups  xmmword ptr [rcx+50h], xmm1
0x1800165c8  movups  xmm0, xmmword ptr [rax+60h]
0x1800165cc  movups  xmmword ptr [rcx+60h], xmm0
0x1800165d0  movups  xmm1, xmmword ptr [rax+70h]
0x1800165d4  add     rax, r8
0x1800165d7  movups  xmmword ptr [rcx+70h], xmm1
0x1800165db  add     rcx, r8
0x1800165de  sub     rdx, 1
0x1800165e2  jnz     short loc_18001659A
0x1800165e4  movups  xmm0, xmmword ptr [rax]
0x1800165e7  mov     rsi, [rsp+28h+arg_8]
0x1800165ec  movups  xmmword ptr [rcx], xmm0
0x1800165ef  movups  xmm1, xmmword ptr [rax+10h]
0x1800165f3  movups  xmmword ptr [rcx+10h], xmm1
0x1800165f7  movups  xmm0, xmmword ptr [rax+20h]
0x1800165fb  movups  xmmword ptr [rcx+20h], xmm0
0x1800165ff  movups  xmm1, xmmword ptr [rax+30h]
0x180016603  movups  xmmword ptr [rcx+30h], xmm1
0x180016607  movups  xmm0, xmmword ptr [rax+40h]
0x18001660b  mov     rax, [rbx+4E0h]
0x180016612  mov     [rbx+4D0h], rax
0x180016619  mov     [rbx+4D8h], rbx
0x180016620  mov     rbx, [rsp+28h+arg_0]
0x180016625  movups  xmmword ptr [rcx+40h], xmm0
0x180016629  add     rsp, 20h
0x18001662d  pop     rdi
0x18001662e  retn
```
