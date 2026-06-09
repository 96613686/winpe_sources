# Dfdll::CMutex::get_MutexHandle(void * &)

- ea: `0x180012748`
- end: `0x1800127ce`
- name: `?get_MutexHandle@CMutex@Dfdll@@IEAAJAEAPEAX@Z`
- size: `134`
- prototype: `__int64 __fastcall(Dfdll::CMutex *__hidden this, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800126a0`
- `0x180012700`

## callees

- `0x180012748`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012788`
- `KERNEL32!GetLastError` at `0x180012788`
- `KERNEL32!CloseHandle` at `0x1800127ad`
- `KERNEL32!CloseHandle` at `0x1800127ad`
- `KERNEL32!CreateMutexW` at `0x18001277a`
- `KERNEL32!CreateMutexW` at `0x18001277a`

## pseudocode

```c
__int64 __fastcall Dfdll::CMutex::get_MutexHandle(Dfdll::CMutex *this, void **a2)
{
  __int64 v4; // rax
  const WCHAR *v5; // r8
  HANDLE MutexW; // rdi
  signed int LastError; // eax
  signed int v8; // ecx

  if ( *((_QWORD *)this + 3) )
  {
LABEL_11:
    *a2 = (void *)*((_QWORD *)this + 3);
    return 0;
  }
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
    v5 = *(const WCHAR **)(v4 + 16);
  else
    v5 = 0;
  MutexW = CreateMutexW(0, 0, v5);
  if ( MutexW )
    goto LABEL_15;
  LastError = GetLastError();
  v8 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v8 = LastError;
  if ( v8 >= 0 )
  {
LABEL_15:
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 3, (signed __int64)MutexW, 0) )
      CloseHandle(MutexW);
    goto LABEL_11;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180012748  mov     [rsp+arg_0], rbx
0x18001274d  mov     [rsp+arg_8], rsi
0x180012752  push    rdi
0x180012753  sub     rsp, 20h
0x180012757  mov     rsi, rdx
0x18001275a  mov     rbx, rcx
0x18001275d  cmp     qword ptr [rcx+18h], 0
0x180012762  jnz     short loc_1800127B3
0x180012764  mov     rax, [rcx+10h]
0x180012768  test    rax, rax
0x18001276b  jnz     short loc_180012772
0x18001276d  xor     r8d, r8d
0x180012770  jmp     short loc_180012776
0x180012772  mov     r8, [rax+10h]; lpName
0x180012776  xor     edx, edx; bInitialOwner
0x180012778  xor     ecx, ecx; lpMutexAttributes
0x18001277a  call    cs:__imp_CreateMutexW
0x180012780  mov     rdi, rax
0x180012783  test    rax, rax
0x180012786  jnz     short loc_1800127A0
0x180012788  call    cs:__imp_GetLastError
0x18001278e  movzx   ecx, ax
0x180012791  or      ecx, 80070000h
0x180012797  test    eax, eax
0x180012799  cmovle  ecx, eax
0x18001279c  test    ecx, ecx
0x18001279e  js      short loc_1800127BC
0x1800127a0  xor     eax, eax
0x1800127a2  lock cmpxchg [rbx+18h], rdi
0x1800127a8  jz      short loc_1800127B3
0x1800127aa  mov     rcx, rdi; hObject
0x1800127ad  call    cs:__imp_CloseHandle
0x1800127b3  mov     rax, [rbx+18h]
0x1800127b7  mov     [rsi], rax
0x1800127ba  xor     ecx, ecx
0x1800127bc  mov     eax, ecx
0x1800127be  mov     rbx, [rsp+28h+arg_0]
0x1800127c3  mov     rsi, [rsp+28h+arg_8]
0x1800127c8  add     rsp, 20h
0x1800127cc  pop     rdi
0x1800127cd  retn
```
