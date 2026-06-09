# CRdpWindowTracker::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x14005f888`
- end: `0x14005fb15`
- name: `?WndProc@CRdpWindowTracker@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `653`
- prototype: `__int64 __fastcall(CRdpWindowTracker *__hidden this, HWND hWnd, UINT Msg, UINT_PTR uIDEvent, LPARAM lParam)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x14005ee60`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x1400081ac`
- `0x1400081d0`
- `0x14000d350`
- `0x14000efb8`
- `0x14005e17c`
- `0x14005f470`
- `0x14005f888`
- `0x14006b010`

## import_xrefs

- `USER32!DefWindowProcW` at `0x14005f922`
- `USER32!DefWindowProcW` at `0x14005f922`
- `USER32!KillTimer` at `0x14005fa7d`
- `USER32!KillTimer` at `0x14005fa7d`

## string_xrefs

- `0x14005f8e6`: `UpdateAllGeometries() failed`
- `0x14005f9c3`: `UpdateAllGeometries() failed`
- `0x14005fadf`: `UpdateAllGeometries() failed`

## pseudocode

```c
LRESULT __fastcall CRdpWindowTracker::WndProc(
        CRdpWindowTracker *this,
        HWND hWnd,
        UINT Msg,
        UINT_PTR uIDEvent,
        LPARAM lParam)
{
  int updated; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int IsDefaultDesktopInteractive; // esi
  __int64 v13; // rbx
  int v14; // esi
  unsigned int v15; // eax
  CTSCriticalSection *v16; // rbx
  BOOL v17; // esi
  int v18; // ebx
  unsigned int v19; // eax
  __int64 v20; // [rsp+30h] [rbp-10h] BYREF
  CTSCriticalSection *v21; // [rsp+38h] [rbp-8h] BYREF

  switch ( Msg )
  {
    case 0x401u:
      updated = CRdpWindowTracker::UpdateAllGeometries(this);
      if ( updated < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            93,
            (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"UpdateAllGeometries() failed",
            updated);
        }
        return DefWindowProcW(hWnd, Msg, uIDEvent, lParam);
      }
      break;
    case 0x2B1u:
      v20 = 0;
      IsDefaultDesktopInteractive = CRdpWindowTracker::IsDefaultDesktopInteractive(this);
      v21 = (CRdpWindowTracker *)((char *)this + 56);
      CTSCriticalSection::Lock((CRdpWindowTracker *)((char *)this + 56));
      v13 = 0;
      if ( *((_QWORD *)this + 9) )
      {
        TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v20);
        v13 = *((_QWORD *)this + 9);
        v20 = v13;
        TCntPtr<IRdrVirtualChannel>::SafeAddRef(&v20);
      }
      *((_DWORD *)this + 60) = IsDefaultDesktopInteractive;
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v21);
      v14 = CRdpWindowTracker::UpdateAllGeometries(this);
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            94,
            (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
            v15,
            (__int64)"UpdateAllGeometries() failed",
            v14);
        }
        TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v20);
        return DefWindowProcW(hWnd, Msg, uIDEvent, lParam);
      }
      if ( v13 )
        (*(void (__fastcall **)(__int64, unsigned __int64, _QWORD))(*(_QWORD *)v13 + 40LL))(
          v13,
          ((unsigned __int64)this + 48) & -(__int64)(this != 0),
          0);
      TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v20);
      break;
    case 0x113u:
      v16 = (CRdpWindowTracker *)((char *)this + 56);
      v17 = 0;
      v21 = (CRdpWindowTracker *)((char *)this + 56);
      CTSCriticalSection::Lock((CRdpWindowTracker *)((char *)this + 56));
      if ( *((_DWORD *)this + 74) )
        v17 = uIDEvent == *((_QWORD *)this + 38);
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v21);
      if ( !v17 )
        return DefWindowProcW(hWnd, Msg, uIDEvent, lParam);
      KillTimer(hWnd, uIDEvent);
      v21 = v16;
      CTSCriticalSection::Lock(v16);
      *((_DWORD *)this + 74) = 0;
      *((_QWORD *)this + 38) = 0;
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v21);
      v18 = CRdpWindowTracker::UpdateAllGeometries(this);
      if ( v18 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          95,
          (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
          v19,
          (__int64)"UpdateAllGeometries() failed",
          v18);
      }
      break;
    default:
      return DefWindowProcW(hWnd, Msg, uIDEvent, lParam);
  }
  return 0;
}

```

## disassembly

```asm
0x14005f888  push    rbp
0x14005f88a  push    rbx
0x14005f88b  push    rsi
0x14005f88c  push    rdi
0x14005f88d  push    r12
0x14005f88f  push    r14
0x14005f891  push    r15
0x14005f893  mov     rbp, rsp
0x14005f896  sub     rsp, 40h
0x14005f89a  mov     r15, r9
0x14005f89d  mov     r14d, r8d
0x14005f8a0  mov     r12, rdx
0x14005f8a3  mov     rdi, rcx
0x14005f8a6  cmp     r8d, 401h
0x14005f8ad  jnz     loc_14005F937
0x14005f8b3  call    ?UpdateAllGeometries@CRdpWindowTracker@@AEAAJXZ; CRdpWindowTracker::UpdateAllGeometries(void)
0x14005f8b8  mov     ebx, eax
0x14005f8ba  test    eax, eax
0x14005f8bc  jns     loc_14005FB0E
0x14005f8c2  mov     rdx, cs:WPP_GLOBAL_Control
0x14005f8c9  lea     rcx, WPP_GLOBAL_Control
0x14005f8d0  cmp     rdx, rcx
0x14005f8d3  jz      short loc_14005F915
0x14005f8d5  test    byte ptr [rdx+1Ch], 8
0x14005f8d9  jz      short loc_14005F915
0x14005f8db  cmp     byte ptr [rdx+19h], 2
0x14005f8df  jb      short loc_14005F915
0x14005f8e1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005f8e6  lea     rcx, aUpdateallgeome; "UpdateAllGeometries() failed"
0x14005f8ed  mov     [rsp+40h+var_18], ebx
0x14005f8f1  mov     [rsp+40h+var_20], rcx
0x14005f8f6  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005f8fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f904  mov     edx, 5Dh ; ']'
0x14005f909  mov     r9d, eax
0x14005f90c  mov     rcx, [rcx+10h]
0x14005f910  call    WPP_SF_DsD
0x14005f915  mov     r9, [rbp+lParam]; lParam
0x14005f919  mov     r8, r15; wParam
0x14005f91c  mov     edx, r14d; Msg
0x14005f91f  mov     rcx, r12; hWnd
0x14005f922  call    cs:__imp_DefWindowProcW
0x14005f928  add     rsp, 40h
0x14005f92c  pop     r15
0x14005f92e  pop     r14
0x14005f930  pop     r12
0x14005f932  pop     rdi
0x14005f933  pop     rsi
0x14005f934  pop     rbx
0x14005f935  pop     rbp
0x14005f936  retn
0x14005f937  cmp     r14d, 2B1h
0x14005f93e  jnz     loc_14005FA32
0x14005f944  mov     [rbp+var_10], 0
0x14005f94c  call    ?IsDefaultDesktopInteractive@CRdpWindowTracker@@AEAAHXZ; CRdpWindowTracker::IsDefaultDesktopInteractive(void)
0x14005f951  lea     rcx, [rdi+38h]; this
0x14005f955  mov     esi, eax
0x14005f957  mov     [rbp+var_8], rcx
0x14005f95b  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14005f960  xor     ebx, ebx
0x14005f962  cmp     [rdi+48h], rbx
0x14005f966  jz      short loc_14005F982
0x14005f968  lea     rcx, [rbp+var_10]
0x14005f96c  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14005f971  mov     rbx, [rdi+48h]
0x14005f975  lea     rcx, [rbp+var_10]
0x14005f979  mov     [rbp+var_10], rbx
0x14005f97d  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x14005f982  lea     rcx, [rbp+var_8]; this
0x14005f986  mov     [rdi+0F0h], esi
0x14005f98c  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14005f991  mov     rcx, rdi; this
0x14005f994  call    ?UpdateAllGeometries@CRdpWindowTracker@@AEAAJXZ; CRdpWindowTracker::UpdateAllGeometries(void)
0x14005f999  mov     esi, eax
0x14005f99b  test    eax, eax
0x14005f99d  jns     short loc_14005FA00
0x14005f99f  mov     rdx, cs:WPP_GLOBAL_Control
0x14005f9a6  lea     rcx, WPP_GLOBAL_Control
0x14005f9ad  cmp     rdx, rcx
0x14005f9b0  jz      short loc_14005F9F2
0x14005f9b2  test    byte ptr [rdx+1Ch], 8
0x14005f9b6  jz      short loc_14005F9F2
0x14005f9b8  cmp     byte ptr [rdx+19h], 2
0x14005f9bc  jb      short loc_14005F9F2
0x14005f9be  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005f9c3  lea     rcx, aUpdateallgeome; "UpdateAllGeometries() failed"
0x14005f9ca  mov     [rsp+40h+var_18], esi
0x14005f9ce  mov     [rsp+40h+var_20], rcx
0x14005f9d3  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005f9da  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f9e1  mov     edx, 5Eh ; '^'
0x14005f9e6  mov     r9d, eax
0x14005f9e9  mov     rcx, [rcx+10h]
0x14005f9ed  call    WPP_SF_DsD
0x14005f9f2  lea     rcx, [rbp+var_10]
0x14005f9f6  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14005f9fb  jmp     loc_14005F915
0x14005fa00  test    rbx, rbx
0x14005fa03  jz      short loc_14005FA24
0x14005fa05  mov     r9, [rbx]
0x14005fa08  lea     rax, [rdi+30h]
0x14005fa0c  neg     rdi
0x14005fa0f  mov     rcx, rbx
0x14005fa12  sbb     rdx, rdx
0x14005fa15  xor     r8d, r8d
0x14005fa18  and     rdx, rax
0x14005fa1b  mov     rax, [r9+28h]
0x14005fa1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005fa24  lea     rcx, [rbp+var_10]
0x14005fa28  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14005fa2d  jmp     loc_14005FB0E
0x14005fa32  cmp     r14d, 113h
0x14005fa39  jnz     loc_14005F915
0x14005fa3f  lea     rbx, [rcx+38h]
0x14005fa43  xor     esi, esi
0x14005fa45  mov     rcx, rbx; this
0x14005fa48  mov     [rbp+var_8], rbx
0x14005fa4c  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14005fa51  cmp     [rdi+128h], esi
0x14005fa57  jz      short loc_14005FA66
0x14005fa59  cmp     r15, [rdi+130h]
0x14005fa60  lea     eax, [rsi+1]
0x14005fa63  cmovz   esi, eax
0x14005fa66  lea     rcx, [rbp+var_8]; this
0x14005fa6a  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14005fa6f  test    esi, esi
0x14005fa71  jz      loc_14005F915
0x14005fa77  mov     rdx, r15; uIDEvent
0x14005fa7a  mov     rcx, r12; hWnd
0x14005fa7d  call    cs:__imp_KillTimer
0x14005fa83  mov     rcx, rbx; this
0x14005fa86  mov     [rbp+var_8], rbx
0x14005fa8a  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14005fa8f  lea     rcx, [rbp+var_8]; this
0x14005fa93  mov     dword ptr [rdi+128h], 0
0x14005fa9d  mov     qword ptr [rdi+130h], 0
0x14005faa8  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14005faad  mov     rcx, rdi; this
0x14005fab0  call    ?UpdateAllGeometries@CRdpWindowTracker@@AEAAJXZ; CRdpWindowTracker::UpdateAllGeometries(void)
0x14005fab5  mov     ebx, eax
0x14005fab7  test    eax, eax
0x14005fab9  jns     short loc_14005FB0E
0x14005fabb  mov     rdx, cs:WPP_GLOBAL_Control
0x14005fac2  lea     rcx, WPP_GLOBAL_Control
0x14005fac9  cmp     rdx, rcx
0x14005facc  jz      short loc_14005FB0E
0x14005face  test    byte ptr [rdx+1Ch], 8
0x14005fad2  jz      short loc_14005FB0E
0x14005fad4  cmp     byte ptr [rdx+19h], 2
0x14005fad8  jb      short loc_14005FB0E
0x14005fada  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005fadf  lea     rcx, aUpdateallgeome; "UpdateAllGeometries() failed"
0x14005fae6  mov     [rsp+40h+var_18], ebx
0x14005faea  mov     [rsp+40h+var_20], rcx
0x14005faef  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005faf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fafd  mov     edx, 5Fh ; '_'
0x14005fb02  mov     r9d, eax
0x14005fb05  mov     rcx, [rcx+10h]
0x14005fb09  call    WPP_SF_DsD
0x14005fb0e  xor     eax, eax
0x14005fb10  jmp     loc_14005F928
```
