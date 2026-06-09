# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)

- ea: `0x14000eee0`
- end: `0x14000f03f`
- name: `?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z`
- size: `351`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140011020`
- `0x1400110d0`

## callees

- `0x14000eee0`
- `0x1400187b0`
- `0x140034b10`
- `0x140034c58`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000ef12`
- `KERNEL32!SetLastError` at `0x14000ef12`
- `KERNEL32!GetCurrentThreadId` at `0x14000ef5e`
- `KERNEL32!GetCurrentThreadId` at `0x14000ef5e`
- `KERNEL32!LeaveCriticalSection` at `0x14000ef99`
- `KERNEL32!LeaveCriticalSection` at `0x14000ef99`
- `KERNEL32!EnterCriticalSection` at `0x14000ef74`
- `KERNEL32!EnterCriticalSection` at `0x14000ef74`
- `USER32!CreateWindowExW` at `0x14000f023`
- `USER32!CreateWindowExW` at `0x14000f023`

## pseudocode

```c
HWND __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(
        HMENU a1,
        __int64 a2,
        struct tagRECT *a3,
        const WCHAR *a4,
        DWORD dwStyle,
        DWORD dwExStyle,
        HMENU a7,
        unsigned __int16 a8)
{
  AtlThunkData_t *Data; // rax
  unsigned int v13; // edx
  HMENU hMenu; // rcx
  struct tagRECT *v15; // rax

  Data = (AtlThunkData_t *)*((_QWORD *)a1 + 5);
  if ( !Data )
  {
    Data = AtlThunk_AllocateData();
    *((_QWORD *)a1 + 5) = Data;
    if ( !Data )
    {
      SetLastError(0xEu);
      return 0;
    }
  }
  AtlThunk_InitData(Data, 0, 0);
  if ( !a8 )
    return 0;
  if ( a1 == (HMENU)-16LL || !a1 )
  {
    ATL::_AtlRaiseException(0xC0000005, v13);
    JUMPOUT(0x14000F03ELL);
  }
  *((_QWORD *)a1 + 2) = a1;
  *((_DWORD *)a1 + 6) = GetCurrentThreadId();
  EnterCriticalSection(&stru_140063978);
  *((_QWORD *)a1 + 4) = qword_1400639A0;
  qword_1400639A0 = (__int64)(a1 + 4);
  LeaveCriticalSection(&stru_140063978);
  hMenu = a7;
  if ( !a7 && (dwStyle & 0x40000000) != 0 )
    hMenu = a1;
  v15 = &ATL::CWindow::rcDefault;
  if ( a3 )
    v15 = a3;
  return CreateWindowExW(
           dwExStyle,
           (LPCWSTR)a8,
           a4,
           dwStyle,
           v15->left,
           v15->top,
           v15->right - v15->left,
           v15->bottom - v15->top,
           0,
           hMenu,
           hInstance,
           0);
}

```

## disassembly

```asm
0x14000eee0  push    rbx
0x14000eee2  push    rsi
0x14000eee3  push    rdi
0x14000eee4  push    r14
0x14000eee6  push    r15
0x14000eee8  sub     rsp, 60h
0x14000eeec  mov     rax, [rcx+28h]
0x14000eef0  xor     r15d, r15d
0x14000eef3  mov     r14, r9
0x14000eef6  mov     rbx, r8
0x14000eef9  mov     rdi, rcx
0x14000eefc  test    rax, rax
0x14000eeff  jnz     short loc_14000EF2D
0x14000ef01  call    AtlThunk_AllocateData
0x14000ef06  mov     [rdi+28h], rax
0x14000ef0a  test    rax, rax
0x14000ef0d  jnz     short loc_14000EF2D
0x14000ef0f  lea     ecx, [rax+0Eh]; dwErrCode
0x14000ef12  call    cs:__imp_SetLastError
0x14000ef19  nop     dword ptr [rax+rax+00h]
0x14000ef1e  xor     eax, eax
0x14000ef20  add     rsp, 60h
0x14000ef24  pop     r15
0x14000ef26  pop     r14
0x14000ef28  pop     rdi
0x14000ef29  pop     rsi
0x14000ef2a  pop     rbx
0x14000ef2b  retn
0x14000ef2d  xor     r8d, r8d; FirstParameter
0x14000ef30  xor     edx, edx; Proc
0x14000ef32  mov     rcx, rax; Thunk
0x14000ef35  call    AtlThunk_InitData
0x14000ef3a  cmp     [rsp+88h+arg_38], r15w
0x14000ef43  jz      short loc_14000EF1E
0x14000ef45  lea     rsi, [rdi+10h]
0x14000ef49  test    rsi, rsi
0x14000ef4c  jz      loc_14000F034
0x14000ef52  test    rdi, rdi
0x14000ef55  jz      loc_14000F034
0x14000ef5b  mov     [rsi], rdi
0x14000ef5e  call    cs:__imp_GetCurrentThreadId
0x14000ef65  nop     dword ptr [rax+rax+00h]
0x14000ef6a  lea     rcx, stru_140063978; lpCriticalSection
0x14000ef71  mov     [rsi+8], eax
0x14000ef74  call    cs:__imp_EnterCriticalSection
0x14000ef7b  nop     dword ptr [rax+rax+00h]
0x14000ef80  mov     rax, cs:qword_1400639A0
0x14000ef87  lea     rcx, stru_140063978; lpCriticalSection
0x14000ef8e  mov     [rsi+10h], rax
0x14000ef92  mov     cs:qword_1400639A0, rsi
0x14000ef99  call    cs:__imp_LeaveCriticalSection
0x14000efa0  nop     dword ptr [rax+rax+00h]
0x14000efa5  mov     rcx, [rsp+88h+arg_30]
0x14000efad  mov     r9d, [rsp+88h+dwStyle]; dwStyle
0x14000efb5  test    rcx, rcx
0x14000efb8  jnz     short loc_14000EFC3
0x14000efba  bt      r9d, 1Eh
0x14000efbf  cmovb   rcx, rdi
0x14000efc3  mov     r10, cs:hInstance
0x14000efca  lea     rax, ?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x14000efd1  movzx   edx, [rsp+88h+arg_38]; lpClassName
0x14000efd9  test    rbx, rbx
0x14000efdc  mov     [rsp+88h+lpParam], r15; lpParam
0x14000efe1  cmovnz  rax, rbx
0x14000efe5  mov     [rsp+88h+hInstance], r10; hInstance
0x14000efea  mov     [rsp+88h+hMenu], rcx; hMenu
0x14000efef  mov     ecx, [rsp+88h+dwExStyle]; dwExStyle
0x14000eff6  mov     [rsp+88h+hWndParent], r15; hWndParent
0x14000effb  mov     ebx, [rax+4]
0x14000effe  mov     r8d, [rax+8]
0x14000f002  mov     edi, [rax]
0x14000f004  sub     r8d, edi
0x14000f007  mov     r11d, [rax+0Ch]
0x14000f00b  sub     r11d, ebx
0x14000f00e  mov     [rsp+88h+nHeight], r11d; nHeight
0x14000f013  mov     [rsp+88h+nWidth], r8d; nWidth
0x14000f018  mov     r8, r14; lpWindowName
0x14000f01b  mov     [rsp+88h+Y], ebx; Y
0x14000f01f  mov     [rsp+88h+X], edi; X
0x14000f023  call    cs:__imp_CreateWindowExW
0x14000f02a  nop     dword ptr [rax+rax+00h]
0x14000f02f  jmp     loc_14000EF20
0x14000f034  mov     ecx, 0C0000005h; unsigned int
0x14000f039  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
