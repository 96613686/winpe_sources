# DockingProviders::EndQueryVisibleDocks(unsigned __int64)

- ea: `0x180014e20`
- end: `0x18001508e`
- name: `?EndQueryVisibleDocks@DockingProviders@@QEAAJ_K@Z`
- size: `622`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, void *Block)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18000c680`
- `0x180018b80`
- `0x180019260`

## callees

- `0x180001124`
- `0x1800014d0`
- `0x18000c308`
- `0x18000c348`
- `0x18000d460`
- `0x180010664`
- `0x180014e20`
- `0x18001ca70`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014eec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014eec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015046`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015046`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014f25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014f25`

## pseudocode

```c
__int64 __fastcall DockingProviders::EndQueryVisibleDocks(PSRWLOCK SRWLock, void *Block)
{
  int v4; // esi
  __int64 i; // rbp
  __int64 v6; // r14
  __int64 v7; // r12
  __int64 v8; // rdi
  signed int v9; // eax
  signed int v10; // edi
  bool v11; // sf
  PSRWLOCK v13; // [rsp+38h] [rbp-50h] BYREF
  char v14; // [rsp+40h] [rbp-48h]

  if ( (unsigned int)dword_180026010 > 5
    && (qword_180026020 & 0x200000000000LL) != 0
    && (qword_180026028 & 0x200000000000LL) == qword_180026028 )
  {
    tlgWriteTransfer_EventWriteTransfer(&dword_180026010, byte_180021F69, 0, 0, 2, &v13);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, Block);
  }
  v13 = SRWLock;
  AcquireSRWLockShared(SRWLock);
  v14 = 1;
  if ( Block )
  {
    v4 = 0;
    for ( i = 0; (unsigned int)i < *((_DWORD *)Block + 10); i = (unsigned int)(i + 1) )
    {
      v6 = *((_QWORD *)SRWLock[3].Ptr + i);
      EnterCriticalSection((LPCRITICAL_SECTION)Block);
      v7 = *((_QWORD *)Block + 6);
      LeaveCriticalSection((LPCRITICAL_SECTION)Block);
      if ( *(_QWORD *)(v6 + 112) )
      {
        v8 = *(_QWORD *)(v7 + 8 * i);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, v6, v8);
        }
        v9 = (*(__int64 (__fastcall **)(__int64))(v6 + 112))(v8);
        v10 = v9;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, v6, v9);
        }
        v11 = v10 < 0;
        if ( v10 > 0 )
        {
          v10 = (unsigned __int16)v10 | 0x80070000;
          v11 = v10 < 0;
        }
        if ( v11 && v4 >= 0 )
          v4 = v10;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25)
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, v6);
      }
    }
    ReadLock::~ReadLock((ReadLock *)&v13);
    operator delete(*((void **)Block + 6));
    operator delete(*((void **)Block + 7));
    operator delete(*((void **)Block + 8));
    DeleteCriticalSection((LPCRITICAL_SECTION)Block);
    operator delete(Block);
    return (unsigned int)v4;
  }
  else
  {
    ReadLock::~ReadLock((ReadLock *)&v13);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180014e20  mov     r11, rsp
0x180014e23  mov     [r11+10h], rbx
0x180014e27  mov     [r11+18h], rbp
0x180014e2b  push    rsi
0x180014e2c  push    rdi
0x180014e2d  push    r12
0x180014e2f  push    r14
0x180014e31  push    r15
0x180014e33  sub     rsp, 60h
0x180014e37  mov     rax, cs:__security_cookie
0x180014e3e  xor     rax, rsp
0x180014e41  mov     [rsp+88h+var_30], rax
0x180014e46  mov     rbx, rdx
0x180014e49  mov     r15, rcx
0x180014e4c  mov     eax, cs:dword_180026010
0x180014e52  cmp     eax, 5
0x180014e55  jbe     short loc_180014EA8
0x180014e57  mov     rdx, cs:qword_180026028
0x180014e5e  mov     rax, cs:qword_180026020
0x180014e65  mov     rcx, 200000000000h
0x180014e6f  test    rcx, rax
0x180014e72  jz      short loc_180014EA8
0x180014e74  mov     rax, rdx
0x180014e77  and     rax, rcx
0x180014e7a  cmp     rax, rdx
0x180014e7d  jnz     short loc_180014EA8
0x180014e7f  lea     rax, [r11-50h]
0x180014e83  mov     [r11-60h], rax
0x180014e87  mov     dword ptr [rsp+88h+var_68], 2
0x180014e8f  xor     r9d, r9d
0x180014e92  xor     r8d, r8d
0x180014e95  lea     rdx, byte_180021F69
0x180014e9c  lea     rcx, dword_180026010
0x180014ea3  call    _tlgWriteTransfer_EventWriteTransfer
0x180014ea8  mov     [rsp+88h+var_58], rbx
0x180014ead  lea     rax, WPP_GLOBAL_Control
0x180014eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ebb  cmp     rcx, rax
0x180014ebe  jz      short loc_180014EE4
0x180014ec0  cmp     byte ptr [rcx+19h], 3
0x180014ec4  jb      short loc_180014EE4
0x180014ec6  test    byte ptr [rcx+1Ch], 1
0x180014eca  jz      short loc_180014EE4
0x180014ecc  mov     edx, 4Bh ; 'K'
0x180014ed1  mov     r9, rbx
0x180014ed4  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180014edb  mov     rcx, [rcx+10h]
0x180014edf  call    WPP_SF_q
0x180014ee4  mov     [rsp+88h+var_50], r15
0x180014ee9  mov     rcx, r15; SRWLock
0x180014eec  call    cs:__imp_AcquireSRWLockShared
0x180014ef2  mov     [rsp+88h+var_48], 1
0x180014ef7  test    rbx, rbx
0x180014efa  jz      loc_180015058
0x180014f00  xor     esi, esi
0x180014f02  xor     ebp, ebp
0x180014f04  cmp     [rbx+28h], esi
0x180014f07  jbe     loc_18001501D
0x180014f0d  mov     rax, [r15+18h]
0x180014f11  mov     r14, [rax+rbp*8]
0x180014f15  mov     rcx, rbx; lpCriticalSection
0x180014f18  call    cs:__imp_EnterCriticalSection
0x180014f1e  mov     r12, [rbx+30h]
0x180014f22  mov     rcx, rbx; lpCriticalSection
0x180014f25  call    cs:__imp_LeaveCriticalSection
0x180014f2b  cmp     qword ptr [r14+70h], 0
0x180014f30  jnz     short loc_180014F7A
0x180014f32  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f39  lea     r12, WPP_GLOBAL_Control
0x180014f40  cmp     rcx, r12
0x180014f43  jz      loc_180015012
0x180014f49  cmp     byte ptr [rcx+19h], 1
0x180014f4d  jb      loc_180015012
0x180014f53  test    byte ptr [rcx+1Ch], 1
0x180014f57  jz      loc_180015012
0x180014f5d  mov     edx, 14h
0x180014f62  mov     r9, r14
0x180014f65  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180014f6c  mov     rcx, [rcx+10h]
0x180014f70  call    WPP_SF_q
0x180014f75  jmp     loc_180015012
0x180014f7a  mov     rdi, [r12+rbp*8]
0x180014f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f85  lea     r12, WPP_GLOBAL_Control
0x180014f8c  cmp     rcx, r12
0x180014f8f  jz      short loc_180014FBA
0x180014f91  cmp     byte ptr [rcx+19h], 4
0x180014f95  jb      short loc_180014FBA
0x180014f97  test    byte ptr [rcx+1Ch], 1
0x180014f9b  jz      short loc_180014FBA
0x180014f9d  mov     edx, 15h
0x180014fa2  mov     [rsp+88h+var_68], rdi
0x180014fa7  mov     r9, r14
0x180014faa  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180014fb1  mov     rcx, [rcx+10h]
0x180014fb5  call    WPP_SF_qq
0x180014fba  mov     rcx, rdi
0x180014fbd  mov     rax, [r14+70h]
0x180014fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fc6  mov     edi, eax
0x180014fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fcf  cmp     rcx, r12
0x180014fd2  jz      short loc_180014FFC
0x180014fd4  cmp     byte ptr [rcx+19h], 4
0x180014fd8  jb      short loc_180014FFC
0x180014fda  test    byte ptr [rcx+1Ch], 1
0x180014fde  jz      short loc_180014FFC
0x180014fe0  mov     edx, 16h
0x180014fe5  mov     dword ptr [rsp+88h+var_68], eax
0x180014fe9  mov     r9, r14
0x180014fec  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180014ff3  mov     rcx, [rcx+10h]
0x180014ff7  call    WPP_SF_qD
0x180014ffc  test    edi, edi
0x180014ffe  jle     short loc_18001500B
0x180015000  movzx   edi, di
0x180015003  or      edi, 80070000h
0x180015009  test    edi, edi
0x18001500b  jns     short loc_180015012
0x18001500d  test    esi, esi
0x18001500f  cmovns  esi, edi
0x180015012  inc     ebp
0x180015014  cmp     ebp, [rbx+28h]
0x180015017  jb      loc_180014F0D
0x18001501d  lea     rcx, [rsp+88h+var_50]; this
0x180015022  call    ??1ReadLock@@QEAA@XZ; ReadLock::~ReadLock(void)
0x180015027  nop
0x180015028  mov     rcx, [rbx+30h]; Block
0x18001502c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015031  mov     rcx, [rbx+38h]; Block
0x180015035  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001503a  mov     rcx, [rbx+40h]; Block
0x18001503e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015043  mov     rcx, rbx; lpCriticalSection
0x180015046  call    cs:__imp_DeleteCriticalSection
0x18001504c  mov     rcx, rbx; Block
0x18001504f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015054  mov     eax, esi
0x180015056  jmp     short loc_180015068
0x180015058  lea     rcx, [rsp+88h+var_50]; this
0x18001505d  call    ??1ReadLock@@QEAA@XZ; ReadLock::~ReadLock(void)
0x180015062  nop
0x180015063  mov     eax, 80070057h
0x180015068  mov     rcx, [rsp+88h+var_30]
0x18001506d  xor     rcx, rsp; StackCookie
0x180015070  call    __security_check_cookie
0x180015075  lea     r11, [rsp+88h+var_28]
0x18001507a  mov     rbx, [r11+38h]
0x18001507e  mov     rbp, [r11+40h]
0x180015082  mov     rsp, r11
0x180015085  pop     r15
0x180015087  pop     r14
0x180015089  pop     r12
0x18001508b  pop     rdi
0x18001508c  pop     rsi
0x18001508d  retn
```
