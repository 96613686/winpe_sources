# CscCompleteBufferingStateChangeRequest

- ea: `0x1400874b0`
- end: `0x140087916`
- name: `CscCompleteBufferingStateChangeRequest`
- size: `1126`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400017c0`
- `0x140003a00`
- `0x1400084f0`
- `0x14000e070`
- `0x1400169d4`
- `0x140018930`
- `0x140018b50`
- `0x140019204`
- `0x14001a624`
- `0x140020168`
- `0x1400202b8`
- `0x14002f010`
- `0x14002f0f0`
- `0x1400501e8`
- `0x1400874b0`

## import_xrefs

- `rdbss!RxAcquirePowerContextLock` at `0x14008787b`
- `rdbss!RxAcquirePowerContextLock` at `0x14008787b`
- `rdbss!RxUpdateFcbPowerState` at `0x1400878a0`
- `rdbss!RxUpdateFcbPowerState` at `0x1400878a0`
- `rdbss!RxReleasePowerContextLock` at `0x1400878ac`
- `rdbss!RxReleasePowerContextLock` at `0x1400878ac`

## pseudocode

```c
__int64 __fastcall CscCompleteBufferingStateChangeRequest(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rbx
  bool v4; // r14
  char v5; // r15
  int v6; // r9d
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // ebx
  char v11; // r14
  int v12; // eax
  int v13; // eax
  __int64 v14; // r14
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  char v18; // al
  __int64 v20; // [rsp+60h] [rbp-29h] BYREF
  __int128 v21; // [rsp+68h] [rbp-21h] BYREF
  __int128 v22; // [rsp+90h] [rbp+7h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(a1 + 72);
  v4 = *(_QWORD *)(a1 + 80) != (_QWORD)CscDeviceObject;
  v5 = *(_BYTE *)(a1 + 464);
  v22 = 0;
  v21 = 0;
  CscGetContextsEx(0, v2, &v21);
  LOBYTE(v6) = 1;
  CscUpdateAndCaptureConnectionStateEx(v2, v3, a1, v6, (__int64)&v22, 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LOBYTE(v8) = (*(_DWORD *)(v2 + 232) & 0x10) != 0 ? 89 : 78;
    LOBYTE(v7) = (v5 & 8) != 0 ? 89 : 78;
    LOBYTE(v9) = v4 ? 89 : 78;
    WPP_SF_cqqDDDcc(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      v8,
      v9,
      v2,
      v3,
      *(_DWORD *)(v2 + 156),
      *(_DWORD *)(v2 + 164),
      *(_DWORD *)(v2 + 160),
      (_BYTE)v7,
      (_BYTE)v8);
  }
  if ( (BYTE1(v22) & 0x40) != 0 )
  {
    v10 = CscDetermineAbortStatus(&v22);
  }
  else
  {
    v10 = 0;
    if ( v4 && (v22 & 0x10) == 0 )
    {
      v11 = 0;
      if ( (v5 & 8) != 0 && (unsigned __int8)CscCheckRdrStatusTransitionIfNetErr(3221225480LL, &v22, v2) )
      {
        *(_BYTE *)(a1 + 464) &= ~8u;
        v11 = 1;
      }
      if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 408LL) )
      {
        if ( (*(_DWORD *)(a1 + 128) & 2) != 0 )
        {
          v10 = -1073741536;
        }
        else
        {
          *(_OWORD *)(a1 + 208) = 0;
          *(_OWORD *)(a1 + 224) = 0;
          *(_QWORD *)(a1 + 240) = 0;
          v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 408LL))(a1);
        }
      }
      else
      {
        v10 = -1073741822;
      }
      if ( v11 )
      {
        v10 &= -((BYTE1(v22) & 0x40) != 0);
      }
      else if ( (v10 & 0x80000000) == 0 )
      {
        v20 = 0;
        if ( (v22 & 0x20) != 0 )
        {
          v12 = *(_DWORD *)(a1 + 456);
          if ( (v12 & 2) != 0 || (v12 & 1) != 0 )
          {
            v13 = *(_DWORD *)(a1 + 460);
            if ( (v13 & 2) == 0 && (v13 & 1) == 0 && (*(_DWORD *)(v2 + 232) & 0x10) == 0 )
            {
              v14 = *((_QWORD *)&v21 + 1);
              if ( (*(_DWORD *)(*((_QWORD *)&v21 + 1) + 4LL) & 0x8000) == 0 )
              {
                if ( (unsigned __int8)CscOKToMarkSparseOnOplockBreak(v2 + 360, *((_QWORD *)&v21 + 1))
                  || (BYTE1(v22) & 2) != 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                  {
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_bb4d19251b293a160bd8737ecbaa6d46_Traceguids);
                  }
                  v20 = 0x2000000000LL;
                  v15 = CscStoreSetInformationEntry(*(_QWORD *)(v14 + 56), (__int64)&v20, 0, 0, 0, 0, 0);
                  if ( v15 >= 0 )
                  {
                    RxAcquirePowerContextLock();
                    v18 = *(_BYTE *)(v2 + 282);
                    if ( (v18 & 1) != 0 )
                    {
                      LOBYTE(v16) = 1;
                      LOBYTE(v17) = 4;
                      if ( v18 >= 0 )
                        LOBYTE(v17) = 2;
                      RxUpdateFcbPowerState(v2, v16, v17);
                    }
                    RxReleasePowerContextLock();
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      return v10;
                    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        18,
                        WPP_bb4d19251b293a160bd8737ecbaa6d46_Traceguids,
                        (unsigned int)v15);
                  }
                }
                else if ( *(_DWORD *)(v14 + 32) || (*(_BYTE *)(a1 + 464) & 0x10) != 0 )
                {
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    return v10;
                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                    WPP_SF_Z(
                      WPP_GLOBAL_Control->AttachedDevice,
                      16,
                      WPP_bb4d19251b293a160bd8737ecbaa6d46_Traceguids,
                      v2 + 360);
                }
                else
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                  {
                    WPP_SF_Z(
                      WPP_GLOBAL_Control->AttachedDevice,
                      15,
                      WPP_bb4d19251b293a160bd8737ecbaa6d46_Traceguids,
                      v2 + 360);
                  }
                  CscCloseServerStateAndUpdateTime(v2);
                  CscTransitionFcbOffline(v2, 0, 8, 0);
                  *(_QWORD *)(v14 + 64) = MEMORY[0xFFFFF78000000014] + 100000000LL;
                }
              }
            }
          }
        }
      }
      else if ( (unsigned __int8)CscCheckRdrStatusTransitionIfNetErr(v10, &v22, v2) && (BYTE1(v22) & 0x40) == 0 )
      {
        v10 = 0;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_bb4d19251b293a160bd8737ecbaa6d46_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x1400874b0  push    rbp
0x1400874b2  push    rbx
0x1400874b3  push    rsi
0x1400874b4  push    rdi
0x1400874b5  push    r14
0x1400874b7  push    r15
0x1400874b9  lea     rbp, [rsp-2Fh]
0x1400874be  sub     rsp, 0B8h
0x1400874c5  mov     rax, cs:__security_cookie
0x1400874cc  xor     rax, rsp
0x1400874cf  mov     [rbp+57h+var_40], rax
0x1400874d3  mov     rax, cs:CscDeviceObject
0x1400874da  lea     r8, [rbp+57h+var_78]
0x1400874de  cmp     [rcx+50h], rax
0x1400874e2  mov     rsi, rcx
0x1400874e5  mov     rdi, [rcx+38h]
0x1400874e9  xorps   xmm0, xmm0
0x1400874ec  mov     rbx, [rcx+48h]
0x1400874f0  setnz   r14b
0x1400874f4  mov     r15b, [rcx+1D0h]
0x1400874fb  xorps   xmm1, xmm1
0x1400874fe  xor     ecx, ecx
0x140087500  mov     rdx, rdi
0x140087503  movups  [rbp+57h+var_50], xmm0
0x140087507  movups  [rbp+57h+var_78], xmm1
0x14008750b  call    CscGetContextsEx
0x140087510  lea     rax, [rbp+57h+var_50]
0x140087514  mov     byte ptr [rsp+0E0h+var_B8], 1
0x140087519  mov     r9b, 1
0x14008751c  mov     [rsp+0E0h+var_C0], rax
0x140087521  mov     r8, rsi
0x140087524  mov     rdx, rbx
0x140087527  mov     rcx, rdi
0x14008752a  call    CscUpdateAndCaptureConnectionStateEx
0x14008752f  mov     rcx, cs:WPP_GLOBAL_Control
0x140087536  lea     rax, WPP_GLOBAL_Control
0x14008753d  cmp     rcx, rax
0x140087540  jz      short loc_1400875B9
0x140087542  mov     eax, [rcx+2Ch]
0x140087545  test    al, 20h
0x140087547  jz      short loc_1400875B9
0x140087549  mov     eax, [rdi+0E8h]
0x14008754f  mov     r11b, 0Bh
0x140087552  mov     rcx, [rcx+18h]
0x140087556  and     al, 10h
0x140087558  neg     al
0x14008755a  mov     r10b, 4Eh ; 'N'
0x14008755d  mov     al, r15b
0x140087560  sbb     r8b, r8b
0x140087563  and     al, 8
0x140087565  and     r8b, r11b
0x140087568  add     r8b, r10b
0x14008756b  neg     al
0x14008756d  mov     [rsp+0E0h+var_90], r8b
0x140087572  mov     al, r14b
0x140087575  sbb     dl, dl
0x140087577  and     dl, r11b
0x14008757a  add     dl, r10b
0x14008757d  mov     [rsp+0E0h+var_98], dl
0x140087581  neg     al
0x140087583  mov     eax, [rdi+0A0h]
0x140087589  mov     [rsp+0E0h+var_A0], eax
0x14008758d  sbb     r9b, r9b
0x140087590  mov     eax, [rdi+0A4h]
0x140087596  and     r9b, r11b
0x140087599  mov     [rsp+0E0h+var_A8], eax
0x14008759d  add     r9b, r10b
0x1400875a0  mov     eax, [rdi+9Ch]
0x1400875a6  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1400875aa  mov     [rsp+0E0h+var_B8], rbx
0x1400875af  mov     [rsp+0E0h+var_C0], rdi
0x1400875b4  call    WPP_SF_cqqDDDcc
0x1400875b9  test    byte ptr [rbp+57h+var_50+1], 40h
0x1400875bd  jz      short loc_1400875CF
0x1400875bf  lea     rcx, [rbp+57h+var_50]
0x1400875c3  call    CscDetermineAbortStatus
0x1400875c8  mov     ebx, eax
0x1400875ca  jmp     loc_1400878C5
0x1400875cf  xor     ebx, ebx
0x1400875d1  test    r14b, r14b
0x1400875d4  jz      loc_1400878C5
0x1400875da  test    byte ptr [rbp+57h+var_50], 10h
0x1400875de  jnz     loc_1400878C5
0x1400875e4  xor     r14b, r14b
0x1400875e7  test    r15b, 8
0x1400875eb  jz      short loc_14008760C
0x1400875ed  mov     r8, rdi
0x1400875f0  lea     rdx, [rbp+57h+var_50]
0x1400875f4  mov     ecx, 0C0000008h
0x1400875f9  call    CscCheckRdrStatusTransitionIfNetErr
0x1400875fe  test    al, al
0x140087600  jz      short loc_14008760C
0x140087602  and     byte ptr [rsi+1D0h], 0F7h
0x140087609  mov     r14b, 1
0x14008760c  mov     rax, [rsi+50h]
0x140087610  mov     rcx, [rax+160h]
0x140087617  cmp     [rcx+198h], rbx
0x14008761e  jnz     short loc_140087627
0x140087620  mov     ebx, 0C0000002h
0x140087625  jmp     short loc_14008766E
0x140087627  mov     eax, [rsi+80h]
0x14008762d  test    al, 2
0x14008762f  jnz     short loc_140087669
0x140087631  xor     eax, eax
0x140087633  xorps   xmm0, xmm0
0x140087636  movups  xmmword ptr [rsi+0D0h], xmm0
0x14008763d  movups  xmmword ptr [rsi+0E0h], xmm0
0x140087644  mov     [rsi+0F0h], rax
0x14008764b  mov     rax, [rsi+50h]
0x14008764f  mov     rcx, [rax+160h]
0x140087656  mov     rax, [rcx+198h]
0x14008765d  mov     rcx, rsi
0x140087660  call    _guard_dispatch_icall
0x140087665  mov     ebx, eax
0x140087667  jmp     short loc_14008766E
0x140087669  mov     ebx, 0C0000120h
0x14008766e  test    r14b, r14b
0x140087671  jnz     loc_1400878BA
0x140087677  test    ebx, ebx
0x140087679  jns     short loc_1400876A9
0x14008767b  mov     r8, rdi
0x14008767e  lea     rdx, [rbp+57h+var_50]
0x140087682  mov     ecx, ebx
0x140087684  call    CscCheckRdrStatusTransitionIfNetErr
0x140087689  test    al, al
0x14008768b  jz      loc_1400878C5
0x140087691  test    byte ptr [rbp+57h+var_50+1], 40h
0x140087695  lea     rsi, WPP_GLOBAL_Control
0x14008769c  jnz     loc_1400878CC
0x1400876a2  xor     ebx, ebx
0x1400876a4  jmp     loc_1400878CC
0x1400876a9  test    byte ptr [rbp+57h+var_50], 20h
0x1400876ad  mov     [rbp+57h+var_80], 0
0x1400876b5  jz      loc_1400878C5
0x1400876bb  mov     eax, [rsi+1C8h]
0x1400876c1  test    al, 2
0x1400876c3  jnz     short loc_1400876CD
0x1400876c5  test    al, 1
0x1400876c7  jz      loc_1400878C5
0x1400876cd  mov     eax, [rsi+1CCh]
0x1400876d3  test    al, 2
0x1400876d5  jnz     loc_1400878C5
0x1400876db  test    al, 1
0x1400876dd  jnz     loc_1400878C5
0x1400876e3  mov     eax, [rdi+0E8h]
0x1400876e9  test    al, 10h
0x1400876eb  jnz     loc_1400878C5
0x1400876f1  mov     r14, qword ptr [rbp+57h+var_78+8]
0x1400876f5  test    dword ptr [r14+4], 8000h
0x1400876fd  jnz     loc_1400878C5
0x140087703  lea     r15, [rdi+168h]
0x14008770a  mov     rdx, r14
0x14008770d  mov     rcx, r15
0x140087710  call    CscOKToMarkSparseOnOplockBreak
0x140087715  test    al, al
0x140087717  jnz     loc_1400877DA
0x14008771d  test    byte ptr [rbp+57h+var_50+1], 2
0x140087721  jnz     loc_1400877DA
0x140087727  cmp     dword ptr [r14+20h], 0
0x14008772c  jnz     short loc_14008779B
0x14008772e  test    byte ptr [rsi+1D0h], 10h
0x140087735  jnz     short loc_14008779B
0x140087737  mov     rcx, cs:WPP_GLOBAL_Control
0x14008773e  lea     rsi, WPP_GLOBAL_Control
0x140087745  cmp     rcx, rsi
0x140087748  jz      short loc_140087769
0x14008774a  mov     eax, [rcx+2Ch]
0x14008774d  test    al, 20h
0x14008774f  jz      short loc_140087769
0x140087751  mov     rcx, [rcx+18h]
0x140087755  lea     r8, WPP_bb4d19251b293a160bd8737ecbaa6d46_Traceguids
0x14008775c  mov     edx, 0Fh
0x140087761  mov     r9, r15
0x140087764  call    WPP_SF_Z
0x140087769  mov     rcx, rdi
0x14008776c  call    CscCloseServerStateAndUpdateTime
0x140087771  xor     r9d, r9d
0x140087774  xor     edx, edx
0x140087776  mov     rcx, rdi
0x140087779  lea     r8d, [r9+8]
0x14008777d  call    CscTransitionFcbOffline
0x140087782  mov     rax, ds:0FFFFF78000000014h
0x14008778c  add     rax, 5F5E100h
0x140087792  mov     [r14+40h], rax
0x140087796  jmp     loc_1400878CC
0x14008779b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400877a2  lea     rsi, WPP_GLOBAL_Control
0x1400877a9  cmp     rcx, rsi
0x1400877ac  jz      loc_1400878F7
0x1400877b2  mov     eax, [rcx+2Ch]
0x1400877b5  test    al, 20h
0x1400877b7  jz      loc_1400878CC
0x1400877bd  mov     rcx, [rcx+18h]
0x1400877c1  lea     r8, WPP_bb4d19251b293a160bd8737ecbaa6d46_Traceguids
0x1400877c8  mov     edx, 10h
0x1400877cd  mov     r9, r15
0x1400877d0  call    WPP_SF_Z
0x1400877d5  jmp     loc_1400878CC
0x1400877da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400877e1  lea     rsi, WPP_GLOBAL_Control
0x1400877e8  cmp     rcx, rsi
0x1400877eb  jz      short loc_140087809
0x1400877ed  mov     eax, [rcx+2Ch]
0x1400877f0  test    al, 20h
0x1400877f2  jz      short loc_140087809
0x1400877f4  mov     rcx, [rcx+18h]
0x1400877f8  lea     r8, WPP_bb4d19251b293a160bd8737ecbaa6d46_Traceguids
0x1400877ff  mov     edx, 11h
0x140087804  call    WPP_SF_
0x140087809  mov     dword ptr [rbp+57h+var_80], 0
0x140087810  lea     rdx, [rbp+57h+var_80]
0x140087814  mov     dword ptr [rbp+57h+var_80+4], 20h ; ' '
0x14008781b  xor     r9d, r9d
0x14008781e  mov     rcx, [r14+38h]
0x140087822  xor     r8d, r8d
0x140087825  mov     [rsp+0E0h+var_B0], 0
0x14008782e  mov     [rsp+0E0h+var_B8], 0
0x140087837  mov     [rsp+0E0h+var_C0], 0
0x140087840  call    CscStoreSetInformationEntry
0x140087845  test    eax, eax
0x140087847  jns     short loc_14008787B
0x140087849  mov     rcx, cs:WPP_GLOBAL_Control
0x140087850  cmp     rcx, rsi
0x140087853  jz      loc_1400878F7
0x140087859  mov     edx, [rcx+2Ch]
0x14008785c  test    dl, 20h
0x14008785f  jz      short loc_1400878CC
0x140087861  mov     rcx, [rcx+18h]
0x140087865  lea     r8, WPP_bb4d19251b293a160bd8737ecbaa6d46_Traceguids
0x14008786c  mov     edx, 12h
0x140087871  mov     r9d, eax
0x140087874  call    WPP_SF_d
0x140087879  jmp     short loc_1400878CC
0x14008787b  call    cs:__imp_RxAcquirePowerContextLock
0x140087882  nop     dword ptr [rax+rax+00h]
0x140087887  mov     al, [rdi+11Ah]
0x14008788d  test    al, 1
0x14008788f  jz      short loc_1400878AC
0x140087891  mov     dl, 1
0x140087893  mov     rcx, rdi
0x140087896  mov     r8b, 4
0x140087899  test    al, al
0x14008789b  js      short loc_1400878A0
0x14008789d  mov     r8b, 2
0x1400878a0  call    cs:__imp_RxUpdateFcbPowerState
0x1400878a7  nop     dword ptr [rax+rax+00h]
0x1400878ac  call    cs:__imp_RxReleasePowerContextLock
0x1400878b3  nop     dword ptr [rax+rax+00h]
0x1400878b8  jmp     short loc_1400878CC
0x1400878ba  mov     al, byte ptr [rbp+57h+var_50+1]
0x1400878bd  and     al, 40h
0x1400878bf  neg     al
0x1400878c1  sbb     eax, eax
0x1400878c3  and     ebx, eax
0x1400878c5  lea     rsi, WPP_GLOBAL_Control
0x1400878cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400878d3  cmp     rcx, rsi
0x1400878d6  jz      short loc_1400878F7
0x1400878d8  mov     eax, [rcx+2Ch]
0x1400878db  test    al, 20h
0x1400878dd  jz      short loc_1400878F7
0x1400878df  mov     rcx, [rcx+18h]
0x1400878e3  lea     r8, WPP_bb4d19251b293a160bd8737ecbaa6d46_Traceguids
0x1400878ea  mov     edx, 13h
0x1400878ef  mov     r9d, ebx
0x1400878f2  call    WPP_SF_d
0x1400878f7  mov     eax, ebx
0x1400878f9  mov     rcx, [rbp+57h+var_40]
0x1400878fd  xor     rcx, rsp; StackCookie
0x140087900  call    __security_check_cookie
0x140087905  add     rsp, 0B8h
0x14008790c  pop     r15
0x14008790e  pop     r14
0x140087910  pop     rdi
0x140087911  pop     rsi
0x140087912  pop     rbx
0x140087913  pop     rbp
0x140087914  retn
```
