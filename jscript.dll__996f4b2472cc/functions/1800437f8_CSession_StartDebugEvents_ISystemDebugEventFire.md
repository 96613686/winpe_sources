# CSession::StartDebugEvents(ISystemDebugEventFire *)

- ea: `0x1800437f8`
- end: `0x180043913`
- name: `?StartDebugEvents@CSession@@QEAAJPEAUISystemDebugEventFire@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(CSession *__hidden this, struct ISystemDebugEventFire *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800525d0`

## callees

- `0x1800437f8`
- `0x18004391c`
- `0x1800966aa`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18004386b`
- `KERNEL32!GetCurrentThreadId` at `0x18004386b`
- `KERNEL32!GetCurrentProcessId` at `0x180043853`
- `KERNEL32!GetCurrentProcessId` at `0x180043853`
- `KERNEL32!GetTickCount` at `0x180043883`
- `KERNEL32!GetTickCount` at `0x180043883`

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
0x1800437f8  mov     [rsp+arg_8], rbx
0x1800437fd  push    rdi
0x1800437fe  sub     rsp, 80h
0x180043805  mov     rax, cs:__security_cookie
0x18004380c  xor     rax, rsp
0x18004380f  mov     [rsp+88h+var_18], rax
0x180043814  mov     rbx, rcx
0x180043817  test    rdx, rdx
0x18004381a  jz      loc_18004390C
0x180043820  mov     [rcx+408h], rdx
0x180043827  mov     rcx, rdx
0x18004382a  mov     rax, [rdx]
0x18004382d  mov     rax, [rax+8]
0x180043831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043836  movups  xmm0, xmmword ptr cs:aJscript_0; "JScript"
0x18004383d  xor     edx, edx; Val
0x18004383f  lea     rcx, [rsp+88h+var_58]; void *
0x180043844  movdqu  xmmword ptr [rsp+88h+var_68], xmm0
0x18004384a  lea     r8d, [rdx+40h]; Size
0x18004384e  call    memset_0
0x180043853  call    cs:__imp_GetCurrentProcessId
0x18004385a  nop     dword ptr [rax+rax+00h]
0x18004385f  mov     edx, eax; unsigned int
0x180043861  lea     rcx, [rsp+88h+var_68+0Eh]; unsigned __int16 *
0x180043866  call    ?AppendVal@@YAXPEAGK@Z; AppendVal(ushort *,ulong)
0x18004386b  call    cs:__imp_GetCurrentThreadId
0x180043872  nop     dword ptr [rax+rax+00h]
0x180043877  mov     edx, eax; unsigned int
0x180043879  lea     rcx, [rsp+88h+var_48]; unsigned __int16 *
0x18004387e  call    ?AppendVal@@YAXPEAGK@Z; AppendVal(ushort *,ulong)
0x180043883  call    cs:__imp_GetTickCount
0x18004388a  nop     dword ptr [rax+rax+00h]
0x18004388f  mov     edx, eax; unsigned int
0x180043891  lea     rcx, [rsp+88h+var_36]; unsigned __int16 *
0x180043896  call    ?AppendVal@@YAXPEAGK@Z; AppendVal(ushort *,ulong)
0x18004389b  mov     rcx, [rbx+408h]
0x1800438a2  lea     r8, [rsp+88h+var_68]
0x1800438a7  xor     r11d, r11d
0x1800438aa  lea     rdx, DEBUG_EVENT_GUID
0x1800438b1  mov     [rsp+88h+var_24], r11w
0x1800438b7  mov     rax, [rcx]
0x1800438ba  mov     rax, [rax+18h]
0x1800438be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800438c3  mov     edi, eax
0x1800438c5  test    eax, eax
0x1800438c7  js      short loc_1800438EA
0x1800438c9  xor     eax, eax
0x1800438cb  mov     rcx, [rsp+88h+var_18]
0x1800438d0  xor     rcx, rsp; StackCookie
0x1800438d3  call    __security_check_cookie
0x1800438d8  mov     rbx, [rsp+88h+arg_8]
0x1800438e0  add     rsp, 80h
0x1800438e7  pop     rdi
0x1800438e8  retn
0x1800438ea  mov     rcx, [rbx+408h]
0x1800438f1  mov     rdx, [rcx]
0x1800438f4  mov     rax, [rdx+10h]
0x1800438f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800438fd  mov     eax, edi
0x1800438ff  mov     qword ptr [rbx+408h], 0
0x18004390a  jmp     short loc_1800438CB
0x18004390c  mov     eax, 80004005h
0x180043911  jmp     short loc_1800438CB
```
