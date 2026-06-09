# CVPVideoInterfaceHandler::NotifyThreadProc(void)

- ea: `0x180041830`
- end: `0x180041a4f`
- name: `?NotifyThreadProc@CVPVideoInterfaceHandler@@UEAAKXZ`
- size: `543`
- prototype: `__int64 __fastcall(CVPVideoInterfaceHandler *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180025860`
- `0x180041830`
- `0x180045010`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x1800418c0`
- `KERNEL32!WaitForMultipleObjects` at `0x1800418c0`
- `KERNEL32!ResetEvent` at `0x1800418f3`
- `KERNEL32!ResetEvent` at `0x1800418f3`

## pseudocode

```c
__int64 __fastcall CVPVideoInterfaceHandler::NotifyThreadProc(CVPVideoInterfaceHandler *this)
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x17u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  Handles[0] = this->m_NotifyEventHandle;
  Handles[1] = this->m_EndEventHandle;
LABEL_4:
  if ( v2 != &WPP_GLOBAL_Control )
    WPP_SF_((TRACEHANDLE)v2[2], 0x18u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
  while ( 1 )
  {
    v3 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( v3 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x19u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
    ResetEvent(this->m_NotifyEventHandle);
    if ( this->m_Pin->ConnectedTo(this->m_Pin, (IPin **)&v7) >= 0 && v7 )
    {
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v7)(v7, &GUID_c76794a1_d6c5_11d0_9e69_00c04fd7c15b, &v6) < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Bu, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Au, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Cu, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
      goto LABEL_22;
    }
  }
  if ( v3 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Du, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
    return 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Eu, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
    return 0;
  }
}

```

## disassembly

```asm
0x180041830  mov     [rsp-18h+arg_10], rbx
0x180041835  push    rbp
0x180041836  push    rsi
0x180041837  push    rdi
0x180041838  mov     rbp, rsp
0x18004183b  sub     rsp, 30h
0x18004183f  xorps   xmm0, xmm0
0x180041842  mov     [rbp+arg_0], 0
0x18004184a  movups  xmmword ptr [rbp+Handles], xmm0
0x18004184e  mov     rbx, rcx
0x180041851  mov     [rbp+arg_8], 0
0x180041859  mov     rcx, cs:WPP_GLOBAL_Control
0x180041860  lea     rdi, WPP_GLOBAL_Control
0x180041867  lea     rsi, WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids
0x18004186e  cmp     rcx, rdi
0x180041871  jz      short loc_18004188B
0x180041873  mov     rcx, [rcx+10h]
0x180041877  mov     edx, 17h
0x18004187c  mov     r8, rsi
0x18004187f  call    WPP_SF_
0x180041884  mov     rcx, cs:WPP_GLOBAL_Control
0x18004188b  mov     rax, [rbx+58h]
0x18004188f  mov     [rbp+Handles], rax
0x180041893  mov     rax, [rbx+28h]
0x180041897  mov     [rbp+Handles+8], rax
0x18004189b  cmp     rcx, rdi
0x18004189e  jz      short loc_1800418B1
0x1800418a0  mov     rcx, [rcx+10h]
0x1800418a4  mov     edx, 18h
0x1800418a9  mov     r8, rsi
0x1800418ac  call    WPP_SF_
0x1800418b1  xor     r8d, r8d; bWaitAll
0x1800418b4  lea     rdx, [rbp+Handles]; lpHandles
0x1800418b8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800418bc  lea     ecx, [r8+2]; nCount
0x1800418c0  call    cs:__imp_WaitForMultipleObjects
0x1800418c7  nop     dword ptr [rax+rax+00h]
0x1800418cc  test    eax, eax
0x1800418ce  jnz     loc_1800419ED
0x1800418d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800418db  cmp     rcx, rdi
0x1800418de  jz      short loc_1800418EF
0x1800418e0  mov     rcx, [rcx+10h]
0x1800418e4  lea     edx, [rax+19h]
0x1800418e7  mov     r8, rsi
0x1800418ea  call    WPP_SF_
0x1800418ef  mov     rcx, [rbx+58h]; hEvent
0x1800418f3  call    cs:__imp_ResetEvent
0x1800418fa  nop     dword ptr [rax+rax+00h]
0x1800418ff  mov     rcx, [rbx+30h]
0x180041903  lea     rdx, [rbp+arg_8]
0x180041907  mov     rax, [rcx]
0x18004190a  mov     rax, [rax+30h]
0x18004190e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041913  test    eax, eax
0x180041915  js      loc_1800419B6
0x18004191b  mov     rcx, [rbp+arg_8]
0x18004191f  test    rcx, rcx
0x180041922  jz      loc_1800419B6
0x180041928  mov     rax, [rcx]
0x18004192b  lea     r8, [rbp+arg_0]
0x18004192f  lea     rdx, _GUID_c76794a1_d6c5_11d0_9e69_00c04fd7c15b
0x180041936  mov     rax, [rax]
0x180041939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004193e  test    eax, eax
0x180041940  js      short loc_180041981
0x180041942  mov     rcx, cs:WPP_GLOBAL_Control
0x180041949  cmp     rcx, rdi
0x18004194c  jz      short loc_18004195F
0x18004194e  mov     rcx, [rcx+10h]
0x180041952  mov     edx, 1Ah
0x180041957  mov     r8, rsi
0x18004195a  call    WPP_SF_
0x18004195f  mov     rcx, [rbp+arg_0]
0x180041963  mov     rax, [rcx]
0x180041966  mov     rax, [rax+18h]
0x18004196a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004196f  mov     rcx, [rbp+arg_0]
0x180041973  mov     rax, [rcx]
0x180041976  mov     rax, [rax+10h]
0x18004197a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004197f  jmp     short loc_1800419A4
0x180041981  mov     rcx, cs:WPP_GLOBAL_Control
0x180041988  cmp     rcx, rdi
0x18004198b  jz      short loc_1800419A4
0x18004198d  cmp     byte ptr [rcx+19h], 2
0x180041991  jb      short loc_1800419A4
0x180041993  mov     rcx, [rcx+10h]
0x180041997  mov     edx, 1Bh
0x18004199c  mov     r8, rsi
0x18004199f  call    WPP_SF_
0x1800419a4  mov     rcx, [rbp+arg_8]
0x1800419a8  mov     rax, [rcx]
0x1800419ab  mov     rax, [rax+10h]
0x1800419af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419b4  jmp     short loc_1800419E1
0x1800419b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800419bd  cmp     rcx, rdi
0x1800419c0  jz      loc_1800418B1
0x1800419c6  cmp     byte ptr [rcx+19h], 2
0x1800419ca  jb      loc_18004189B
0x1800419d0  mov     rcx, [rcx+10h]
0x1800419d4  mov     edx, 1Ch
0x1800419d9  mov     r8, rsi
0x1800419dc  call    WPP_SF_
0x1800419e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800419e8  jmp     loc_18004189B
0x1800419ed  cmp     eax, 1
0x1800419f0  jz      short loc_180041A19
0x1800419f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800419f9  cmp     rcx, rdi
0x1800419fc  jz      short loc_180041A15
0x1800419fe  cmp     byte ptr [rcx+19h], 1
0x180041a02  jb      short loc_180041A15
0x180041a04  mov     rcx, [rcx+10h]
0x180041a08  mov     edx, 1Eh
0x180041a0d  mov     r8, rsi
0x180041a10  call    WPP_SF_
0x180041a15  xor     eax, eax
0x180041a17  jmp     short loc_180041A41
0x180041a19  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a20  cmp     rcx, rdi
0x180041a23  jz      short loc_180041A3C
0x180041a25  cmp     byte ptr [rcx+19h], 2
0x180041a29  jb      short loc_180041A3C
0x180041a2b  mov     rcx, [rcx+10h]
0x180041a2f  mov     edx, 1Dh
0x180041a34  mov     r8, rsi
0x180041a37  call    WPP_SF_
0x180041a3c  mov     eax, 1
0x180041a41  mov     rbx, [rsp+30h+arg_10]
0x180041a46  add     rsp, 30h
0x180041a4a  pop     rdi
0x180041a4b  pop     rsi
0x180041a4c  pop     rbp
0x180041a4d  retn
```
