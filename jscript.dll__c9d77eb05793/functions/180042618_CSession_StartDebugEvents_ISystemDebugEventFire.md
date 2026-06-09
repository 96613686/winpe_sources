# CSession::StartDebugEvents(ISystemDebugEventFire *)

- ea: `0x180042618`
- end: `0x180042720`
- name: `?StartDebugEvents@CSession@@QEAAJPEAUISystemDebugEventFire@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(CSession *__hidden this, struct ISystemDebugEventFire *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180051880`

## callees

- `0x180042618`
- `0x180042728`
- `0x18009429a`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180042685`
- `KERNEL32!GetCurrentThreadId` at `0x180042685`
- `KERNEL32!GetCurrentProcessId` at `0x180042673`
- `KERNEL32!GetCurrentProcessId` at `0x180042673`
- `KERNEL32!GetTickCount` at `0x180042697`
- `KERNEL32!GetTickCount` at `0x180042697`

## pseudocode

```c
__int64 __fastcall CSession::StartDebugEvents(CSession *this, struct ISystemDebugEventFire *a2)
{
  DWORD CurrentProcessId; // eax
  DWORD CurrentThreadId; // eax
  DWORD TickCount; // eax
  __int64 v6; // rcx
  int v7; // edi
  __int64 result; // rax
  unsigned __int16 v9[8]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v10[16]; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int16 v11[9]; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int16 v12[15]; // [rsp+52h] [rbp-36h] BYREF

  if ( !a2 )
    return 2147500037LL;
  *((_QWORD *)this + 129) = a2;
  (*(void (__fastcall **)(struct ISystemDebugEventFire *))(*(_QWORD *)a2 + 8LL))(a2);
  *(_OWORD *)v9 = *(_OWORD *)L"JScript";
  memset_0(v10, 0, 0x40u);
  CurrentProcessId = GetCurrentProcessId();
  AppendVal(&v9[7], CurrentProcessId);
  CurrentThreadId = GetCurrentThreadId();
  AppendVal(v11, CurrentThreadId);
  TickCount = GetTickCount();
  AppendVal(v12, TickCount);
  v6 = *((_QWORD *)this + 129);
  v12[9] = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned __int16 *))(*(_QWORD *)v6 + 24LL))(
         v6,
         DEBUG_EVENT_GUID,
         v9);
  if ( v7 >= 0 )
    return 0;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 129) + 16LL))(*((_QWORD *)this + 129));
  result = (unsigned int)v7;
  *((_QWORD *)this + 129) = 0;
  return result;
}

```

## disassembly

```asm
0x180042618  mov     [rsp+arg_8], rbx
0x18004261d  push    rdi
0x18004261e  sub     rsp, 80h
0x180042625  mov     rax, cs:__security_cookie
0x18004262c  xor     rax, rsp
0x18004262f  mov     [rsp+88h+var_18], rax
0x180042634  mov     rbx, rcx
0x180042637  test    rdx, rdx
0x18004263a  jz      loc_180042719
0x180042640  mov     [rcx+408h], rdx
0x180042647  mov     rcx, rdx
0x18004264a  mov     rax, [rdx]
0x18004264d  mov     rax, [rax+8]
0x180042651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042656  movups  xmm0, xmmword ptr cs:aJscript_0; "JScript"
0x18004265d  xor     edx, edx; Val
0x18004265f  lea     rcx, [rsp+88h+var_58]; void *
0x180042664  movdqu  xmmword ptr [rsp+88h+var_68], xmm0
0x18004266a  lea     r8d, [rdx+40h]; Size
0x18004266e  call    memset_0
0x180042673  call    cs:__imp_GetCurrentProcessId
0x180042679  mov     edx, eax; unsigned int
0x18004267b  lea     rcx, [rsp+88h+var_68+0Eh]; unsigned __int16 *
0x180042680  call    ?AppendVal@@YAXPEAGK@Z; AppendVal(ushort *,ulong)
0x180042685  call    cs:__imp_GetCurrentThreadId
0x18004268b  mov     edx, eax; unsigned int
0x18004268d  lea     rcx, [rsp+88h+var_48]; unsigned __int16 *
0x180042692  call    ?AppendVal@@YAXPEAGK@Z; AppendVal(ushort *,ulong)
0x180042697  call    cs:__imp_GetTickCount
0x18004269d  mov     edx, eax; unsigned int
0x18004269f  lea     rcx, [rsp+88h+var_36]; unsigned __int16 *
0x1800426a4  call    ?AppendVal@@YAXPEAGK@Z; AppendVal(ushort *,ulong)
0x1800426a9  mov     rcx, [rbx+408h]
0x1800426b0  lea     r8, [rsp+88h+var_68]
0x1800426b5  xor     r11d, r11d
0x1800426b8  lea     rdx, DEBUG_EVENT_GUID
0x1800426bf  mov     [rsp+88h+var_24], r11w
0x1800426c5  mov     rax, [rcx]
0x1800426c8  mov     rax, [rax+18h]
0x1800426cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426d1  mov     edi, eax
0x1800426d3  test    eax, eax
0x1800426d5  js      short loc_1800426F7
0x1800426d7  xor     eax, eax
0x1800426d9  mov     rcx, [rsp+88h+var_18]
0x1800426de  xor     rcx, rsp; StackCookie
0x1800426e1  call    __security_check_cookie
0x1800426e6  mov     rbx, [rsp+88h+arg_8]
0x1800426ee  add     rsp, 80h
0x1800426f5  pop     rdi
0x1800426f6  retn
0x1800426f7  mov     rcx, [rbx+408h]
0x1800426fe  mov     rdx, [rcx]
0x180042701  mov     rax, [rdx+10h]
0x180042705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004270a  mov     eax, edi
0x18004270c  mov     qword ptr [rbx+408h], 0
0x180042717  jmp     short loc_1800426D9
0x180042719  mov     eax, 80004005h
0x18004271e  jmp     short loc_1800426D9
```
