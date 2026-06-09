# CWiGigDAFProviderDevnodeManagement::IsDeviceReady(bool *)

- ea: `0x18000e5a4`
- end: `0x18000e7b8`
- name: `?IsDeviceReady@CWiGigDAFProviderDevnodeManagement@@QEAAJPEA_N@Z`
- size: `532`
- prototype: `__int64 __fastcall(CWiGigDAFProviderDevnodeManagement *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000faa0`

## callees

- `0x18000c308`
- `0x18000c348`
- `0x18000d460`
- `0x18000e5a4`
- `0x1800102ec`
- `0x180016480`
- `0x18001ca3e`
- `0x18001ca70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000e605`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000e689`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000e605`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000e689`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderDevnodeManagement::IsDeviceReady(
        CWiGigDAFProviderDevnodeManagement *this,
        bool *a2)
{
  unsigned int Ptr; // r15d
  __int64 v5; // rdi
  __int64 v6; // rbx
  int ConnectionState; // ebx
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK v10; // [rsp+38h] [rbp-C8h] BYREF
  char v11; // [rsp+40h] [rbp-C0h]
  _BYTE v12[1168]; // [rsp+50h] [rbp-B0h] BYREF

  LODWORD(v9) = 0;
  memset_0(v12, 0, 0x488u);
  v10 = (PSRWLOCK)*((_QWORD *)this + 77);
  AcquireSRWLockShared(v10);
  v11 = 1;
  Ptr = (unsigned int)v10[2].Ptr;
  ReadLock::~ReadLock(&v10);
  v5 = 0;
  if ( Ptr )
  {
    while ( 1 )
    {
      v6 = *((_QWORD *)this + 77);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          91,
          &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids,
          *((_QWORD *)this + 77));
      }
      LODWORD(v9) = 4;
      memset_0(v12, 0, 0x488u);
      v10 = (PSRWLOCK)v6;
      AcquireSRWLockShared((PSRWLOCK)v6);
      v11 = 1;
      if ( (unsigned int)v5 < *(_DWORD *)(v6 + 16) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, v6);
        }
        ConnectionState = DockingProvider::QueryConnectionState(
                            *(DockingProvider **)(*(_QWORD *)(v6 + 24) + 8 * v5),
                            (enum _ConnectionStatus *)&v9,
                            (struct _DOCK_PROFILE *)v12);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            92,
            &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids,
            v6,
            -2147024809);
        }
        ConnectionState = -2147024809;
      }
      ReadLock::~ReadLock(&v10);
      if ( ConnectionState < 0 )
        break;
      if ( (unsigned int)(v9 - 5) <= 1 )
      {
        *a2 = 0;
        return 0;
      }
      v5 = (unsigned int)(v5 + 1);
      if ( (unsigned int)v5 >= Ptr )
        goto LABEL_20;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids,
        this,
        v5,
        ConnectionState,
        v9,
        (_DWORD)v10);
    }
    return (unsigned int)ConnectionState;
  }
  else
  {
LABEL_20:
    *a2 = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x18000e5a4  mov     [rsp-8+arg_10], rbx
0x18000e5a9  mov     [rsp-8+arg_18], rsi
0x18000e5ae  push    rbp
0x18000e5af  push    rdi
0x18000e5b0  push    r13
0x18000e5b2  push    r14
0x18000e5b4  push    r15
0x18000e5b6  lea     rbp, [rsp-3F0h]
0x18000e5be  sub     rsp, 4F0h
0x18000e5c5  mov     rax, cs:__security_cookie
0x18000e5cc  xor     rax, rsp
0x18000e5cf  mov     [rbp+410h+var_30], rax
0x18000e5d6  mov     rsi, rdx
0x18000e5d9  mov     r14, rcx
0x18000e5dc  mov     dword ptr [rsp+510h+var_4E0], 0
0x18000e5e4  xor     edx, edx; Val
0x18000e5e6  mov     r8d, 488h; Size
0x18000e5ec  lea     rcx, [rsp+510h+var_4C0]; void *
0x18000e5f1  call    memset_0
0x18000e5f6  mov     rbx, [r14+268h]
0x18000e5fd  mov     [rsp+510h+var_4D8], rbx
0x18000e602  mov     rcx, rbx; SRWLock
0x18000e605  call    cs:__imp_AcquireSRWLockShared
0x18000e60b  mov     [rsp+510h+var_4D0], 1
0x18000e610  mov     r15d, [rbx+10h]
0x18000e614  lea     rcx, [rsp+510h+var_4D8]; this
0x18000e619  call    ??1ReadLock@@QEAA@XZ; ReadLock::~ReadLock(void)
0x18000e61e  xor     edi, edi
0x18000e620  test    r15d, r15d
0x18000e623  jz      loc_18000E747
0x18000e629  lea     r13, WPP_GLOBAL_Control
0x18000e630  mov     rbx, [r14+268h]
0x18000e637  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e63e  cmp     rcx, r13
0x18000e641  jz      short loc_18000E667
0x18000e643  cmp     byte ptr [rcx+19h], 4
0x18000e647  jb      short loc_18000E667
0x18000e649  test    byte ptr [rcx+1Ch], 1
0x18000e64d  jz      short loc_18000E667
0x18000e64f  mov     edx, 5Bh ; '['
0x18000e654  mov     r9, rbx
0x18000e657  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x18000e65e  mov     rcx, [rcx+10h]
0x18000e662  call    WPP_SF_q
0x18000e667  mov     dword ptr [rsp+510h+var_4E0], 4
0x18000e66f  xor     edx, edx; Val
0x18000e671  mov     r8d, 488h; Size
0x18000e677  lea     rcx, [rsp+510h+var_4C0]; void *
0x18000e67c  call    memset_0
0x18000e681  mov     [rsp+510h+var_4D8], rbx
0x18000e686  mov     rcx, rbx; SRWLock
0x18000e689  call    cs:__imp_AcquireSRWLockShared
0x18000e68f  mov     [rsp+510h+var_4D0], 1
0x18000e694  cmp     edi, [rbx+10h]
0x18000e697  jb      short loc_18000E6D9
0x18000e699  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6a0  cmp     rcx, r13
0x18000e6a3  jz      short loc_18000E6D2
0x18000e6a5  cmp     byte ptr [rcx+19h], 4
0x18000e6a9  jb      short loc_18000E6D2
0x18000e6ab  test    byte ptr [rcx+1Ch], 1
0x18000e6af  jz      short loc_18000E6D2
0x18000e6b1  mov     edx, 5Ch ; '\'
0x18000e6b6  mov     [rsp+510h+var_4F0], 80070057h
0x18000e6be  mov     r9, rbx
0x18000e6c1  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x18000e6c8  mov     rcx, [rcx+10h]
0x18000e6cc  call    WPP_SF_qD
0x18000e6d1  nop
0x18000e6d2  mov     ebx, 80070057h
0x18000e6d7  jmp     short loc_18000E722
0x18000e6d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6e0  cmp     rcx, r13
0x18000e6e3  jz      short loc_18000E709
0x18000e6e5  cmp     byte ptr [rcx+19h], 4
0x18000e6e9  jb      short loc_18000E709
0x18000e6eb  test    byte ptr [rcx+1Ch], 1
0x18000e6ef  jz      short loc_18000E709
0x18000e6f1  mov     edx, 5Dh ; ']'
0x18000e6f6  mov     r9, rbx
0x18000e6f9  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x18000e700  mov     rcx, [rcx+10h]
0x18000e704  call    WPP_SF_q
0x18000e709  mov     rcx, [rbx+18h]
0x18000e70d  lea     r8, [rsp+510h+var_4C0]; struct _DOCK_PROFILE *
0x18000e712  lea     rdx, [rsp+510h+var_4E0]; enum _ConnectionStatus *
0x18000e717  mov     rcx, [rcx+rdi*8]; this
0x18000e71b  call    ?QueryConnectionState@DockingProvider@@QEAAJPEAW4_ConnectionStatus@@PEAU_DOCK_PROFILE@@@Z; DockingProvider::QueryConnectionState(_ConnectionStatus *,_DOCK_PROFILE *)
0x18000e720  mov     ebx, eax
0x18000e722  lea     rcx, [rsp+510h+var_4D8]; this
0x18000e727  call    ??1ReadLock@@QEAA@XZ; ReadLock::~ReadLock(void)
0x18000e72c  test    ebx, ebx
0x18000e72e  js      short loc_18000E77C
0x18000e730  mov     eax, dword ptr [rsp+510h+var_4E0]
0x18000e734  add     eax, 0FFFFFFFBh
0x18000e737  cmp     eax, 1
0x18000e73a  jbe     short loc_18000E777
0x18000e73c  inc     edi
0x18000e73e  cmp     edi, r15d
0x18000e741  jb      loc_18000E630
0x18000e747  mov     byte ptr [rsi], 1
0x18000e74a  xor     eax, eax
0x18000e74c  mov     rcx, [rbp+410h+var_30]
0x18000e753  xor     rcx, rsp; StackCookie
0x18000e756  call    __security_check_cookie
0x18000e75b  lea     r11, [rsp+510h+var_20]
0x18000e763  mov     rbx, [r11+40h]
0x18000e767  mov     rsi, [r11+48h]
0x18000e76b  mov     rsp, r11
0x18000e76e  pop     r15
0x18000e770  pop     r14
0x18000e772  pop     r13
0x18000e774  pop     rdi
0x18000e775  pop     rbp
0x18000e776  retn
0x18000e777  mov     byte ptr [rsi], 0
0x18000e77a  jmp     short loc_18000E74A
0x18000e77c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e783  cmp     rcx, r13
0x18000e786  jz      short loc_18000E7B4
0x18000e788  cmp     byte ptr [rcx+19h], 1
0x18000e78c  jb      short loc_18000E7B4
0x18000e78e  test    byte ptr [rcx+1Ch], 1
0x18000e792  jz      short loc_18000E7B4
0x18000e794  mov     edx, 0Dh
0x18000e799  mov     [rsp+510h+var_4E8], ebx
0x18000e79d  mov     [rsp+510h+var_4F0], edi
0x18000e7a1  mov     r9, r14
0x18000e7a4  lea     r8, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000e7ab  mov     rcx, [rcx+10h]
0x18000e7af  call    WPP_SF_qDd
0x18000e7b4  mov     eax, ebx
0x18000e7b6  jmp     short loc_18000E74C
```
