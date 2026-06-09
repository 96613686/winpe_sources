# CVPVBIInterfaceHandler::NotifyThreadProc(void)

- ea: `0x180041600`
- end: `0x18004181f`
- name: `?NotifyThreadProc@CVPVBIInterfaceHandler@@UEAAKXZ`
- size: `543`
- prototype: `__int64 __fastcall(CVPVBIInterfaceHandler *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180025860`
- `0x180041600`
- `0x180045010`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x180041690`
- `KERNEL32!WaitForMultipleObjects` at `0x180041690`
- `KERNEL32!ResetEvent` at `0x1800416c3`
- `KERNEL32!ResetEvent` at `0x1800416c3`

## pseudocode

```c
__int64 __fastcall CVPVBIInterfaceHandler::NotifyThreadProc(CVPVBIInterfaceHandler *this)
{
  PVOID *v2; // rcx
  DWORD v3; // eax
  HANDLE Handles[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v6; // [rsp+50h] [rbp+20h] BYREF
  __int64 v7; // [rsp+58h] [rbp+28h] BYREF

  v6 = 0;
  *(_OWORD *)Handles = 0;
  v7 = 0;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x24u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  Handles[0] = this->m_NotifyEventHandle;
  Handles[1] = this->m_EndEventHandle;
LABEL_4:
  if ( v2 != &WPP_GLOBAL_Control )
    WPP_SF_((TRACEHANDLE)v2[2], 0x25u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
  while ( 1 )
  {
    v3 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( v3 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x26u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
    ResetEvent(this->m_NotifyEventHandle);
    if ( this->m_Pin->ConnectedTo(this->m_Pin, (IPin **)&v7) >= 0 && v7 )
    {
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v7)(v7, &GUID_ec529b01_1a1f_11d1_bad9_00609744111a, &v6) < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x28u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x27u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
LABEL_22:
      v2 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_4;
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_4;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x29u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
      goto LABEL_22;
    }
  }
  if ( v3 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Au, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
    return 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Bu, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
    return 0;
  }
}

```

## disassembly

```asm
0x180041600  mov     [rsp-18h+arg_10], rbx
0x180041605  push    rbp
0x180041606  push    rsi
0x180041607  push    rdi
0x180041608  mov     rbp, rsp
0x18004160b  sub     rsp, 30h
0x18004160f  xorps   xmm0, xmm0
0x180041612  mov     [rbp+arg_0], 0
0x18004161a  movups  xmmword ptr [rbp+Handles], xmm0
0x18004161e  mov     rbx, rcx
0x180041621  mov     [rbp+arg_8], 0
0x180041629  mov     rcx, cs:WPP_GLOBAL_Control
0x180041630  lea     rdi, WPP_GLOBAL_Control
0x180041637  lea     rsi, WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids
0x18004163e  cmp     rcx, rdi
0x180041641  jz      short loc_18004165B
0x180041643  mov     rcx, [rcx+10h]
0x180041647  mov     edx, 24h ; '$'
0x18004164c  mov     r8, rsi
0x18004164f  call    WPP_SF_
0x180041654  mov     rcx, cs:WPP_GLOBAL_Control
0x18004165b  mov     rax, [rbx+58h]
0x18004165f  mov     [rbp+Handles], rax
0x180041663  mov     rax, [rbx+28h]
0x180041667  mov     [rbp+Handles+8], rax
0x18004166b  cmp     rcx, rdi
0x18004166e  jz      short loc_180041681
0x180041670  mov     rcx, [rcx+10h]
0x180041674  mov     edx, 25h ; '%'
0x180041679  mov     r8, rsi
0x18004167c  call    WPP_SF_
0x180041681  xor     r8d, r8d; bWaitAll
0x180041684  lea     rdx, [rbp+Handles]; lpHandles
0x180041688  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004168c  lea     ecx, [r8+2]; nCount
0x180041690  call    cs:__imp_WaitForMultipleObjects
0x180041697  nop     dword ptr [rax+rax+00h]
0x18004169c  test    eax, eax
0x18004169e  jnz     loc_1800417BD
0x1800416a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800416ab  cmp     rcx, rdi
0x1800416ae  jz      short loc_1800416BF
0x1800416b0  mov     rcx, [rcx+10h]
0x1800416b4  lea     edx, [rax+26h]
0x1800416b7  mov     r8, rsi
0x1800416ba  call    WPP_SF_
0x1800416bf  mov     rcx, [rbx+58h]; hEvent
0x1800416c3  call    cs:__imp_ResetEvent
0x1800416ca  nop     dword ptr [rax+rax+00h]
0x1800416cf  mov     rcx, [rbx+30h]
0x1800416d3  lea     rdx, [rbp+arg_8]
0x1800416d7  mov     rax, [rcx]
0x1800416da  mov     rax, [rax+30h]
0x1800416de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416e3  test    eax, eax
0x1800416e5  js      loc_180041786
0x1800416eb  mov     rcx, [rbp+arg_8]
0x1800416ef  test    rcx, rcx
0x1800416f2  jz      loc_180041786
0x1800416f8  mov     rax, [rcx]
0x1800416fb  lea     r8, [rbp+arg_0]
0x1800416ff  lea     rdx, _GUID_ec529b01_1a1f_11d1_bad9_00609744111a
0x180041706  mov     rax, [rax]
0x180041709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004170e  test    eax, eax
0x180041710  js      short loc_180041751
0x180041712  mov     rcx, cs:WPP_GLOBAL_Control
0x180041719  cmp     rcx, rdi
0x18004171c  jz      short loc_18004172F
0x18004171e  mov     rcx, [rcx+10h]
0x180041722  mov     edx, 27h ; '''
0x180041727  mov     r8, rsi
0x18004172a  call    WPP_SF_
0x18004172f  mov     rcx, [rbp+arg_0]
0x180041733  mov     rax, [rcx]
0x180041736  mov     rax, [rax+18h]
0x18004173a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004173f  mov     rcx, [rbp+arg_0]
0x180041743  mov     rax, [rcx]
0x180041746  mov     rax, [rax+10h]
0x18004174a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004174f  jmp     short loc_180041774
0x180041751  mov     rcx, cs:WPP_GLOBAL_Control
0x180041758  cmp     rcx, rdi
0x18004175b  jz      short loc_180041774
0x18004175d  cmp     byte ptr [rcx+19h], 2
0x180041761  jb      short loc_180041774
0x180041763  mov     rcx, [rcx+10h]
0x180041767  mov     edx, 28h ; '('
0x18004176c  mov     r8, rsi
0x18004176f  call    WPP_SF_
0x180041774  mov     rcx, [rbp+arg_8]
0x180041778  mov     rax, [rcx]
0x18004177b  mov     rax, [rax+10h]
0x18004177f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041784  jmp     short loc_1800417B1
0x180041786  mov     rcx, cs:WPP_GLOBAL_Control
0x18004178d  cmp     rcx, rdi
0x180041790  jz      loc_180041681
0x180041796  cmp     byte ptr [rcx+19h], 2
0x18004179a  jb      loc_18004166B
0x1800417a0  mov     rcx, [rcx+10h]
0x1800417a4  mov     edx, 29h ; ')'
0x1800417a9  mov     r8, rsi
0x1800417ac  call    WPP_SF_
0x1800417b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800417b8  jmp     loc_18004166B
0x1800417bd  cmp     eax, 1
0x1800417c0  jz      short loc_1800417E9
0x1800417c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800417c9  cmp     rcx, rdi
0x1800417cc  jz      short loc_1800417E5
0x1800417ce  cmp     byte ptr [rcx+19h], 1
0x1800417d2  jb      short loc_1800417E5
0x1800417d4  mov     rcx, [rcx+10h]
0x1800417d8  mov     edx, 2Bh ; '+'
0x1800417dd  mov     r8, rsi
0x1800417e0  call    WPP_SF_
0x1800417e5  xor     eax, eax
0x1800417e7  jmp     short loc_180041811
0x1800417e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800417f0  cmp     rcx, rdi
0x1800417f3  jz      short loc_18004180C
0x1800417f5  cmp     byte ptr [rcx+19h], 2
0x1800417f9  jb      short loc_18004180C
0x1800417fb  mov     rcx, [rcx+10h]
0x1800417ff  mov     edx, 2Ah ; '*'
0x180041804  mov     r8, rsi
0x180041807  call    WPP_SF_
0x18004180c  mov     eax, 1
0x180041811  mov     rbx, [rsp+30h+arg_10]
0x180041816  add     rsp, 30h
0x18004181a  pop     rdi
0x18004181b  pop     rsi
0x18004181c  pop     rbp
0x18004181d  retn
```
