# IASTL::IASComponent::fireEvent(IASTL::IASComponent::Event)

- ea: `0x180014fa0`
- end: `0x18001501c`
- name: `?fireEvent@IASComponent@IASTL@@QEAAJW4Event@12@@Z`
- size: `124`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010370`
- `0x180010380`
- `0x180011e90`
- `0x180011ea0`
- `0x180011f70`

## callees

- `0x180014fa0`
- `0x180019010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180014fcb`
- `KERNEL32!EnterCriticalSection` at `0x180014fcb`
- `KERNEL32!LeaveCriticalSection` at `0x180015004`
- `KERNEL32!LeaveCriticalSection` at `0x180015004`

## pseudocode

```c
__int64 __fastcall IASTL::IASComponent::fireEvent(__int64 a1, int a2)
{
  int v4; // esi
  int v5; // ebx

  if ( a2 >= 5 )
    return 2147549183LL;
  v4 = *((_DWORD *)&IASTL::IASComponent::fsm + 4 * a2 + *(int *)(a1 + 64));
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( v4 == *(_DWORD *)(a1 + 64) )
  {
    v5 = 0;
  }
  else if ( v4 == 5 )
  {
    v5 = -2147418113;
  }
  else
  {
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 120LL))(a1, (unsigned int)a2);
    if ( v5 >= 0 )
      *(_DWORD *)(a1 + 64) = v4;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014fa0  push    rbx
0x180014fa2  push    rbp
0x180014fa3  push    rsi
0x180014fa4  push    rdi
0x180014fa5  sub     rsp, 28h
0x180014fa9  movsxd  rbx, edx
0x180014fac  mov     rdi, rcx
0x180014faf  cmp     ebx, 5
0x180014fb2  jge     short loc_18001500E
0x180014fb4  movsxd  rax, dword ptr [rcx+40h]
0x180014fb8  lea     rsi, ?fsm@IASComponent@IASTL@@0QAY03$$CBW4State@12@A; IASTL::IASComponent::State const (near * IASTL::IASComponent::fsm)[4]
0x180014fbf  add     rcx, 10h; lpCriticalSection
0x180014fc3  lea     r9, [rax+rbx*4]
0x180014fc7  mov     esi, [rsi+r9*4]
0x180014fcb  call    cs:__imp_EnterCriticalSection
0x180014fd1  cmp     esi, [rdi+40h]
0x180014fd4  jnz     short loc_180014FDA
0x180014fd6  xor     ebx, ebx
0x180014fd8  jmp     short loc_180015000
0x180014fda  cmp     esi, 5
0x180014fdd  jnz     short loc_180014FE6
0x180014fdf  mov     ebx, 8000FFFFh
0x180014fe4  jmp     short loc_180015000
0x180014fe6  mov     rax, [rdi]
0x180014fe9  mov     edx, ebx
0x180014feb  mov     rcx, rdi
0x180014fee  mov     rax, [rax+78h]
0x180014ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ff7  mov     ebx, eax
0x180014ff9  test    eax, eax
0x180014ffb  js      short loc_180015000
0x180014ffd  mov     [rdi+40h], esi
0x180015000  lea     rcx, [rdi+10h]; lpCriticalSection
0x180015004  call    cs:__imp_LeaveCriticalSection
0x18001500a  mov     eax, ebx
0x18001500c  jmp     short loc_180015013
0x18001500e  mov     eax, 8000FFFFh
0x180015013  add     rsp, 28h
0x180015017  pop     rdi
0x180015018  pop     rsi
0x180015019  pop     rbp
0x18001501a  pop     rbx
0x18001501b  retn
```
