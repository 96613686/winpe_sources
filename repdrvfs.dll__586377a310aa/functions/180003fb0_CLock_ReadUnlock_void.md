# CLock::ReadUnlock(void)

- ea: `0x180003fb0`
- end: `0x1800040b1`
- name: `?ReadUnlock@CLock@@QEAAHXZ`
- size: `257`
- prototype: `__int64 __fastcall(CLock *__hidden this)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180002af0`
- `0x1800032a0`
- `0x1800038f0`
- `0x180003bc0`
- `0x180022620`
- `0x180024f30`
- `0x180025e2c`
- `0x180031180`
- `0x180031270`
- `0x1800324f0`
- `0x18003d380`

## callees

- `0x1800038c0`
- `0x180003fb0`
- `0x18001e1cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004016`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004016`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000402e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000402e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000400c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004063`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000400c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004063`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004092`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004092`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLock::ReadUnlock(CLock *this)
{
  char i; // si
  DWORD CurrentThreadId; // eax
  int j; // edx
  char *v7; // r8

  GetCurrentThreadId();
  for ( i = CriticalSection::acquire_write((CLock *)((char *)this + 64));
        !i;
        i = CriticalSection::acquire_write((CLock *)((char *)this + 64)) )
  {
    Sleep(0x14u);
  }
  if ( --*((_DWORD *)this + 1) >= 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    for ( j = 0; j < 16; ++j )
    {
      v7 = (char *)this + 4 * j;
      if ( *((_DWORD *)v7 + 34) == CurrentThreadId )
      {
        *((_DWORD *)v7 + 34) = 0;
        break;
      }
    }
    if ( *((_DWORD *)this + 1) )
    {
      GetCurrentThreadId();
      goto LABEL_7;
    }
    *((_DWORD *)this + 33) = 0;
    GetCurrentThreadId();
    if ( SetEvent(*((HANDLE *)this + 14)) )
    {
LABEL_7:
      if ( i )
      {
        if ( *((_BYTE *)this + 104) )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
      }
      return 0;
    }
  }
  if ( i )
    CriticalSection::release((CLock *)((char *)this + 64));
  return 2;
}

```

## disassembly

```asm
0x180003fb0  mov     [rsp+arg_8], rbx
0x180003fb5  mov     [rsp+arg_10], rsi
0x180003fba  push    rdi
0x180003fbb  sub     rsp, 30h
0x180003fbf  mov     rbx, rcx
0x180003fc2  call    cs:__imp_GetCurrentThreadId
0x180003fc8  lea     rdi, [rbx+40h]
0x180003fcc  mov     [rsp+38h+var_18], rdi
0x180003fd1  mov     rcx, rdi; this
0x180003fd4  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x180003fd9  movzx   esi, al
0x180003fdc  mov     [rsp+38h+var_10], al
0x180003fe0  test    al, al
0x180003fe2  jz      loc_18000408D
0x180003fe8  sub     dword ptr [rbx+4], 1
0x180003fec  js      short loc_18000406B
0x180003fee  call    cs:__imp_GetCurrentThreadId
0x180003ff4  xor     r9d, r9d
0x180003ff7  mov     edx, r9d
0x180003ffa  cmp     edx, 10h
0x180003ffd  jl      short loc_180004046
0x180003fff  cmp     [rbx+4], r9d
0x180004003  jnz     short loc_180004063
0x180004005  mov     [rbx+84h], r9d
0x18000400c  call    cs:__imp_GetCurrentThreadId
0x180004012  mov     rcx, [rbx+70h]; hEvent
0x180004016  call    cs:__imp_SetEvent
0x18000401c  test    eax, eax
0x18000401e  jz      short loc_18000406B
0x180004020  test    sil, sil
0x180004023  jz      short loc_180004034
0x180004025  cmp     byte ptr [rdi+28h], 0
0x180004029  jz      short loc_180004034
0x18000402b  mov     rcx, rdi; lpCriticalSection
0x18000402e  call    cs:__imp_LeaveCriticalSection
0x180004034  xor     eax, eax
0x180004036  mov     rbx, [rsp+38h+arg_8]
0x18000403b  mov     rsi, [rsp+38h+arg_10]
0x180004040  add     rsp, 30h
0x180004044  pop     rdi
0x180004045  retn
0x180004046  movsxd  rcx, edx
0x180004049  lea     r8, [rbx+rcx*4]
0x18000404d  cmp     [r8+88h], eax
0x180004054  jnz     short loc_18000405F
0x180004056  mov     [r8+88h], r9d
0x18000405d  jmp     short loc_180003FFF
0x18000405f  inc     edx
0x180004061  jmp     short loc_180003FFA
0x180004063  call    cs:__imp_GetCurrentThreadId
0x180004069  jmp     short loc_180004020
0x18000406b  test    sil, sil
0x18000406e  jz      short loc_180004078
0x180004070  mov     rcx, rdi; this
0x180004073  call    ?release@CriticalSection@@QEAA_NXZ; CriticalSection::release(void)
0x180004078  mov     eax, 2
0x18000407d  mov     rbx, [rsp+38h+arg_8]
0x180004082  mov     rsi, [rsp+38h+arg_10]
0x180004087  add     rsp, 30h
0x18000408b  pop     rdi
0x18000408c  retn
0x18000408d  mov     ecx, 14h; dwMilliseconds
0x180004092  call    cs:__imp_Sleep
0x180004098  mov     rcx, rdi; this
0x18000409b  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x1800040a0  movzx   esi, al
0x1800040a3  mov     [rsp+38h+var_10], al
0x1800040a7  test    al, al
0x1800040a9  jz      short loc_18000408D
0x1800040ab  jmp     loc_180003FE8
```
