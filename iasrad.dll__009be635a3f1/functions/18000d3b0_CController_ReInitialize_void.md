# CController::ReInitialize(void)

- ea: `0x18000d3b0`
- end: `0x18000d5a6`
- name: `?ReInitialize@CController@@UEAAJXZ`
- size: `502`
- prototype: `__int64 __fastcall(CController *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800094e4`
- `0x18000d3b0`
- `0x180014e98`
- `0x1800178b8`
- `0x18001d31c`

## string_xrefs

- `0x18000d3f1`: `ReInitializing Radius component`

## pseudocode

```c
__int64 __fastcall CController::ReInitialize(CPacketReceiver **this)
{
  PVOID *v2; // rax
  int Configuration; // edi
  __int64 result; // rax
  unsigned int v5; // ebx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("ReInitializing Radius component");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( this[9] && this[10] && this[20] )
  {
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u && (*((_DWORD *)v2 + 7) & 0x100) != 0 )
    {
      WppDbgPrint("ReInitializing CPacketReceiver class");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    Configuration = CPacketReceiver::LoadConfiguration(this[9]);
    if ( Configuration >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("ReInitializing CRecvFromPipe class");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
      }
      result = CRecvFromPipe::LoadConfiguration(this[10]);
      v5 = result;
      if ( (int)result < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("ReInitialize CRecvFromPipe failed");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
        }
        return v5;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("ReInitialize PacketReceiver failed");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
      }
      return (unsigned int)Configuration;
    }
  }
  else
  {
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 2u && (*((_DWORD *)v2 + 7) & 0x100) != 0 )
    {
      WppDbgPrint("CController::ReInitialize is called without first calling CController::InitNew");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000d3b0  push    rbx
0x18000d3b2  push    rbp
0x18000d3b3  push    rsi
0x18000d3b4  push    rdi
0x18000d3b5  push    r12
0x18000d3b7  push    r15
0x18000d3b9  sub     rsp, 28h
0x18000d3bd  mov     rbx, rcx
0x18000d3c0  mov     rax, cs:WPP_GLOBAL_Control
0x18000d3c7  lea     rbp, WPP_GLOBAL_Control
0x18000d3ce  lea     r15, aNpsrad; "NPSRAD"
0x18000d3d5  mov     esi, 100h
0x18000d3da  lea     r12, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000d3e1  cmp     rax, rbp
0x18000d3e4  jz      short loc_18000D41F
0x18000d3e6  cmp     byte ptr [rax+19h], 4
0x18000d3ea  jb      short loc_18000D41F
0x18000d3ec  test    [rax+1Ch], esi
0x18000d3ef  jz      short loc_18000D41F
0x18000d3f1  lea     rcx, aReinitializing_0; "ReInitializing Radius component"
0x18000d3f8  call    WppDbgPrint
0x18000d3fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d404  mov     edx, 43h ; 'C'
0x18000d409  mov     r9, r15
0x18000d40c  mov     r8, r12
0x18000d40f  mov     rcx, [rcx+10h]
0x18000d413  call    WPP_SF_s
0x18000d418  mov     rax, cs:WPP_GLOBAL_Control
0x18000d41f  cmp     qword ptr [rbx+48h], 0
0x18000d424  jz      loc_18000D55D
0x18000d42a  cmp     qword ptr [rbx+50h], 0
0x18000d42f  jz      loc_18000D55D
0x18000d435  cmp     qword ptr [rbx+0A0h], 0
0x18000d43d  jz      loc_18000D55D
0x18000d443  cmp     rax, rbp
0x18000d446  jz      short loc_18000D47A
0x18000d448  cmp     byte ptr [rax+19h], 4
0x18000d44c  jb      short loc_18000D47A
0x18000d44e  test    [rax+1Ch], esi
0x18000d451  jz      short loc_18000D47A
0x18000d453  lea     rcx, aReinitializing; "ReInitializing CPacketReceiver class"
0x18000d45a  call    WppDbgPrint
0x18000d45f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d466  mov     edx, 45h ; 'E'
0x18000d46b  mov     r9, r15
0x18000d46e  mov     r8, r12
0x18000d471  mov     rcx, [rcx+10h]
0x18000d475  call    WPP_SF_s
0x18000d47a  mov     rcx, [rbx+48h]; this
0x18000d47e  call    ?LoadConfiguration@CPacketReceiver@@AEAAJXZ; CPacketReceiver::LoadConfiguration(void)
0x18000d483  mov     edi, eax
0x18000d485  test    eax, eax
0x18000d487  jns     short loc_18000D4CE
0x18000d489  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d490  cmp     rcx, rbp
0x18000d493  jz      short loc_18000D4C7
0x18000d495  cmp     byte ptr [rcx+19h], 2
0x18000d499  jb      short loc_18000D4C7
0x18000d49b  test    [rcx+1Ch], esi
0x18000d49e  jz      short loc_18000D4C7
0x18000d4a0  lea     rcx, aReinitializePa; "ReInitialize PacketReceiver failed"
0x18000d4a7  call    WppDbgPrint
0x18000d4ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4b3  mov     edx, 46h ; 'F'
0x18000d4b8  mov     r9, r15
0x18000d4bb  mov     r8, r12
0x18000d4be  mov     rcx, [rcx+10h]
0x18000d4c2  call    WPP_SF_s
0x18000d4c7  mov     eax, edi
0x18000d4c9  jmp     loc_18000D599
0x18000d4ce  mov     rax, cs:WPP_GLOBAL_Control
0x18000d4d5  cmp     rax, rbp
0x18000d4d8  jz      short loc_18000D50C
0x18000d4da  cmp     byte ptr [rax+19h], 4
0x18000d4de  jb      short loc_18000D50C
0x18000d4e0  test    [rax+1Ch], esi
0x18000d4e3  jz      short loc_18000D50C
0x18000d4e5  lea     rcx, aReinitializing_1; "ReInitializing CRecvFromPipe class"
0x18000d4ec  call    WppDbgPrint
0x18000d4f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4f8  mov     edx, 47h ; 'G'
0x18000d4fd  mov     r9, r15
0x18000d500  mov     r8, r12
0x18000d503  mov     rcx, [rcx+10h]
0x18000d507  call    WPP_SF_s
0x18000d50c  mov     rcx, [rbx+50h]; this
0x18000d510  call    ?LoadConfiguration@CRecvFromPipe@@AEAAJXZ; CRecvFromPipe::LoadConfiguration(void)
0x18000d515  mov     ebx, eax
0x18000d517  test    eax, eax
0x18000d519  jns     short loc_18000D599
0x18000d51b  mov     rax, cs:WPP_GLOBAL_Control
0x18000d522  cmp     rax, rbp
0x18000d525  jz      short loc_18000D559
0x18000d527  cmp     byte ptr [rax+19h], 2
0x18000d52b  jb      short loc_18000D559
0x18000d52d  test    [rax+1Ch], esi
0x18000d530  jz      short loc_18000D559
0x18000d532  lea     rcx, aReinitializeCr; "ReInitialize CRecvFromPipe failed"
0x18000d539  call    WppDbgPrint
0x18000d53e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d545  mov     edx, 48h ; 'H'
0x18000d54a  mov     r9, r15
0x18000d54d  mov     r8, r12
0x18000d550  mov     rcx, [rcx+10h]
0x18000d554  call    WPP_SF_s
0x18000d559  mov     eax, ebx
0x18000d55b  jmp     short loc_18000D599
0x18000d55d  cmp     rax, rbp
0x18000d560  jz      short loc_18000D594
0x18000d562  cmp     byte ptr [rax+19h], 2
0x18000d566  jb      short loc_18000D594
0x18000d568  test    [rax+1Ch], esi
0x18000d56b  jz      short loc_18000D594
0x18000d56d  lea     rcx, aCcontrollerRei; "CController::ReInitialize is called wit"...
0x18000d574  call    WppDbgPrint
0x18000d579  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d580  mov     edx, 44h ; 'D'
0x18000d585  mov     r9, r15
0x18000d588  mov     r8, r12
0x18000d58b  mov     rcx, [rcx+10h]
0x18000d58f  call    WPP_SF_s
0x18000d594  mov     eax, 8000FFFFh
0x18000d599  add     rsp, 28h
0x18000d59d  pop     r15
0x18000d59f  pop     r12
0x18000d5a1  pop     rdi
0x18000d5a2  pop     rsi
0x18000d5a3  pop     rbp
0x18000d5a4  pop     rbx
0x18000d5a5  retn
```
