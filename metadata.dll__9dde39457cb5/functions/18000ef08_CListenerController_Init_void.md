# CListenerController::Init(void)

- ea: `0x18000ef08`
- end: `0x18000f044`
- name: `?Init@CListenerController@@AEAAJXZ`
- size: `316`
- prototype: `__int64 __fastcall(CListenerController *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f04c`

## callees

- `0x18000ef08`
- `0x180031010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18000efda`
- `KERNEL32!CreateEventW` at `0x18000efda`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000ef37`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000ef37`
- `KERNEL32!GetLastError` at `0x18000ef4a`
- `KERNEL32!GetLastError` at `0x18000efe9`
- `KERNEL32!GetLastError` at `0x18000ef4a`
- `KERNEL32!GetLastError` at `0x18000efe9`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18000ef86`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18000ef86`

## pseudocode

```c
__int64 __fastcall CListenerController::Init(CListenerController *this)
{
  signed int v2; // eax
  signed int SimpleObjectByIDEx; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  *((_DWORD *)this + 2) = 0;
  v8 = 0;
  v7 = 0;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 24), 0x800003E8) )
  {
    *((_DWORD *)this + 5) = 1;
LABEL_6:
    *((_DWORD *)this + 16) = 1;
    SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v8, L"IIS");
    if ( SimpleObjectByIDEx >= 0 )
    {
      SimpleObjectByIDEx = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v8)(
                             v8,
                             &IID_IAdvancedTableDispenser,
                             &v7);
      if ( SimpleObjectByIDEx >= 0 )
      {
        SimpleObjectByIDEx = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v7 + 48LL))(v7, (char *)this + 72);
        if ( SimpleObjectByIDEx >= 0 )
        {
          EventW = CreateEventW(0, 0, 1, 0);
          *((_QWORD *)this + 12) = EventW;
          if ( EventW )
          {
            SimpleObjectByIDEx = 0;
          }
          else
          {
            LastError = GetLastError();
            SimpleObjectByIDEx = LastError;
            if ( LastError > 0 )
              SimpleObjectByIDEx = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
    goto LABEL_13;
  }
  v2 = GetLastError();
  SimpleObjectByIDEx = v2;
  if ( v2 > 0 )
    SimpleObjectByIDEx = (unsigned __int16)v2 | 0x80070000;
  if ( SimpleObjectByIDEx >= 0 )
    goto LABEL_6;
LABEL_13:
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v7 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)SimpleObjectByIDEx;
}

```

## disassembly

```asm
0x18000ef08  mov     [rsp+arg_10], rbx
0x18000ef0d  push    rdi
0x18000ef0e  sub     rsp, 20h
0x18000ef12  mov     rdi, rcx
0x18000ef15  mov     dword ptr [rcx+8], 0
0x18000ef1c  add     rcx, 18h; lpCriticalSection
0x18000ef20  mov     [rsp+28h+arg_8], 0
0x18000ef29  mov     edx, 800003E8h; dwSpinCount
0x18000ef2e  mov     [rsp+28h+arg_0], 0
0x18000ef37  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000ef3d  test    eax, eax
0x18000ef3f  jz      short loc_18000EF4A
0x18000ef41  mov     dword ptr [rdi+14h], 1
0x18000ef48  jmp     short loc_18000EF67
0x18000ef4a  call    cs:__imp_GetLastError
0x18000ef50  mov     ebx, eax
0x18000ef52  test    eax, eax
0x18000ef54  jle     short loc_18000EF5F
0x18000ef56  movzx   ebx, ax
0x18000ef59  or      ebx, 80070000h
0x18000ef5f  test    ebx, ebx
0x18000ef61  js      loc_18000F002
0x18000ef67  lea     r9, aIis; "IIS"
0x18000ef6e  mov     dword ptr [rdi+40h], 1
0x18000ef75  lea     r8, [rsp+28h+arg_8]
0x18000ef7a  mov     ecx, 1
0x18000ef7f  lea     rdx, IID_ISimpleTableDispenser2
0x18000ef86  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18000ef8c  mov     ebx, eax
0x18000ef8e  test    eax, eax
0x18000ef90  js      short loc_18000F002
0x18000ef92  mov     rcx, [rsp+28h+arg_8]
0x18000ef97  lea     r8, [rsp+28h+arg_0]
0x18000ef9c  lea     rdx, IID_IAdvancedTableDispenser
0x18000efa3  mov     rax, [rcx]
0x18000efa6  mov     rax, [rax]
0x18000efa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efae  mov     ebx, eax
0x18000efb0  test    eax, eax
0x18000efb2  js      short loc_18000F002
0x18000efb4  mov     rcx, [rsp+28h+arg_0]
0x18000efb9  lea     rdx, [rdi+48h]
0x18000efbd  mov     rax, [rcx]
0x18000efc0  mov     rax, [rax+30h]
0x18000efc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efc9  mov     ebx, eax
0x18000efcb  test    eax, eax
0x18000efcd  js      short loc_18000F002
0x18000efcf  xor     r9d, r9d; lpName
0x18000efd2  xor     edx, edx; bManualReset
0x18000efd4  xor     ecx, ecx; lpEventAttributes
0x18000efd6  lea     r8d, [r9+1]; bInitialState
0x18000efda  call    cs:__imp_CreateEventW
0x18000efe0  mov     [rdi+60h], rax
0x18000efe4  test    rax, rax
0x18000efe7  jnz     short loc_18000F000
0x18000efe9  call    cs:__imp_GetLastError
0x18000efef  mov     ebx, eax
0x18000eff1  test    eax, eax
0x18000eff3  jle     short loc_18000F002
0x18000eff5  movzx   ebx, ax
0x18000eff8  or      ebx, 80070000h
0x18000effe  jmp     short loc_18000F002
0x18000f000  xor     ebx, ebx
0x18000f002  mov     rcx, [rsp+28h+arg_0]
0x18000f007  test    rcx, rcx
0x18000f00a  jz      short loc_18000F021
0x18000f00c  mov     rax, [rcx]
0x18000f00f  mov     rax, [rax+10h]
0x18000f013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f018  mov     [rsp+28h+arg_0], 0
0x18000f021  mov     rcx, [rsp+28h+arg_8]
0x18000f026  test    rcx, rcx
0x18000f029  jz      short loc_18000F037
0x18000f02b  mov     rax, [rcx]
0x18000f02e  mov     rax, [rax+10h]
0x18000f032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f037  mov     eax, ebx
0x18000f039  mov     rbx, [rsp+28h+arg_10]
0x18000f03e  add     rsp, 20h
0x18000f042  pop     rdi
0x18000f043  retn
```
