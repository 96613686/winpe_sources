# UlSetServerSessionProperty

- ea: `0x1400d7828`
- end: `0x1400d7c6a`
- name: `UlSetServerSessionProperty`
- size: `1090`
- prototype: `__int64 __fastcall(PIRP Irp, __int64, __int64, unsigned int, unsigned int *, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x1400f3180`

## callees

- `0x14000a350`
- `0x1400193f8`
- `0x140074468`
- `0x1400868f0`
- `0x1400869c0`
- `0x1400cb924`
- `0x1400d2918`
- `0x1400d737c`
- `0x1400d7828`
- `0x1400eeb94`
- `0x1400fd240`
- `0x140142df4`
- `0x140146c38`
- `0x140167810`
- `0x140167c40`
- `0x1401c9510`
- `0x1401d9e44`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1400d7a5f`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d7a5f`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d7c0d`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d7c0d`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d78cb`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d78cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7c19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7c19`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d78b8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d78b8`

## pseudocode

```c
__int64 __fastcall UlSetServerSessionProperty(
        PIRP Irp,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  __int64 v10; // rbx
  char v11; // r14
  __int64 ObjectFromOpaqueId; // rax
  __int64 v13; // r8
  __int64 v14; // rdi
  int v15; // ebx
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rcx
  __int128 v19; // xmm0
  BOOLEAN v20; // al
  unsigned int v21; // ecx
  char v22; // r10
  char v23; // r11
  unsigned int v24; // r8d
  char v25; // dl
  __int16 v26; // ax
  __int64 v27; // rsi
  char v28; // cl
  __int64 v29; // rcx
  int v30; // eax
  char v32; // [rsp+50h] [rbp-79h]
  _OWORD v33[5]; // [rsp+60h] [rbp-69h] BYREF
  __int64 v34; // [rsp+B0h] [rbp-19h] BYREF
  int v35; // [rsp+B8h] [rbp-11h]

  v34 = 0;
  v35 = 0;
  memset(v33, 0, sizeof(v33));
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qqiLqL(1033, 30, WPP_77b773efe445301db38c0738c64be0c3_Traceguids, Irp, a2, a3, a4, a5, a6);
  v10 = *(_QWORD *)(a2 + 56);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v10 + 1368));
  v11 = 1;
  ObjectFromOpaqueId = UxGetObjectFromOpaqueId(
                         a3,
                         1,
                         (unsigned int)UlReferenceServerSession,
                         (unsigned int)UlValidateServerSession,
                         a2);
  v14 = ObjectFromOpaqueId;
  if ( !ObjectFromOpaqueId )
    goto LABEL_4;
  if ( *(_WORD *)(ObjectFromOpaqueId + 16) == 1 && !*(_WORD *)(ObjectFromOpaqueId + 18) )
  {
    v15 = -1073741637;
    goto LABEL_49;
  }
  v15 = 0;
  switch ( a4 )
  {
    case 0u:
      goto LABEL_32;
    case 1u:
      v16 = UlConfigLogging(ObjectFromOpaqueId + 128, ObjectFromOpaqueId, a5, Irp);
      goto LABEL_40;
    case 2u:
      v15 = UlCaptureQosParameter(Irp);
      if ( v15 < 0 )
        goto LABEL_49;
      if ( (_DWORD)v34 )
      {
LABEL_4:
        v15 = -1073741811;
        goto LABEL_49;
      }
      v16 = UlQosConfigureFlowCharacteristics(v14 + 104, (char *)&v34 + 4);
      goto LABEL_40;
    case 3u:
      v19 = *(_OWORD *)(a5 + 1);
      if ( (*a5 & 1) != 0 )
      {
        *(_DWORD *)(ObjectFromOpaqueId + 264) = *a5;
        *(_OWORD *)(ObjectFromOpaqueId + 268) = v19;
      }
      else
      {
        *(_OWORD *)(ObjectFromOpaqueId + 264) = 0;
        *(_DWORD *)(ObjectFromOpaqueId + 280) = 0;
      }
      goto LABEL_42;
    case 5u:
      v18 = HIDWORD(*(_QWORD *)a5);
      if ( (unsigned int)v18 <= 1 )
      {
        if ( *(_DWORD *)(ObjectFromOpaqueId + 96) == (_DWORD)v18 )
          v11 = 0;
        else
          *(_QWORD *)(ObjectFromOpaqueId + 92) = *(_QWORD *)a5;
        goto LABEL_42;
      }
      break;
    case 8u:
LABEL_32:
      v20 = IoIs32bitProcess(Irp);
      v21 = *a5;
      v22 = *((_BYTE *)a5 + 9);
      v23 = *((_BYTE *)a5 + 10);
      v24 = a5[1];
      v25 = *((_BYTE *)a5 + 11);
      BYTE8(v33[0]) = *((_BYTE *)a5 + 8);
      BYTE9(v33[0]) = v22;
      BYTE10(v33[0]) = v23;
      v32 = v21;
      *(_QWORD *)&v33[0] = __PAIR64__(v24, v21);
      if ( v20 )
      {
        *((_QWORD *)&v33[2] + 1) = a5[6];
        LOWORD(v33[2]) = *((_WORD *)a5 + 10);
        *((_QWORD *)&v33[1] + 1) = a5[4];
        LOWORD(v33[1]) = *((_WORD *)a5 + 6);
        *((_QWORD *)&v33[3] + 1) = a5[8];
        v26 = *((_WORD *)a5 + 14);
      }
      else
      {
        *((_QWORD *)&v33[2] + 1) = *((_QWORD *)a5 + 5);
        LOWORD(v33[2]) = *((_WORD *)a5 + 16);
        *((_QWORD *)&v33[1] + 1) = *((_QWORD *)a5 + 3);
        LOWORD(v33[1]) = *((_WORD *)a5 + 8);
        *((_QWORD *)&v33[3] + 1) = *((_QWORD *)a5 + 7);
        v26 = *((_WORD *)a5 + 24);
        v32 = v21;
      }
      v27 = *(_QWORD *)(a2 + 56);
      v28 = v25;
      LOWORD(v33[3]) = v26;
      v33[4] = 0;
      if ( a4 != 8 )
        v28 = 0;
      BYTE11(v33[0]) = v28;
      v15 = UlVerifyAuthConfig(v27, v33);
      if ( v15 < 0 )
        goto LABEL_42;
      if ( (v32 & 1) == 0 )
      {
        UlFreeAuthConfig(v14 + 296, 0);
        goto LABEL_42;
      }
      v16 = UlCopyAuthConfig(v27, (int)v14 + 296, (unsigned int)v33, 0, 0, Irp->RequestorMode);
      goto LABEL_40;
    case 9u:
      v17 = *(_QWORD *)a5;
      if ( (*(_QWORD *)a5 & 1) == 0 )
        v17 = 0;
      *(_QWORD *)(v14 + 284) = v17;
      goto LABEL_42;
    case 0xAu:
      v16 = UlCaptureChannelBindConfig(
              *(_QWORD *)(a2 + 56),
              (int)a5,
              0,
              (int)ObjectFromOpaqueId + 376,
              Irp,
              Irp->RequestorMode);
LABEL_40:
      v15 = v16;
      goto LABEL_42;
  }
  v15 = -1073741811;
LABEL_42:
  v29 = *(_QWORD *)(a2 + 56);
  if ( (*(_BYTE *)(v29 + 1761) & 0x20) != 0 )
    McTemplateK0qq_EtwWriteTransfer(v29 + 1688, HTTP_EVENT_SET_SERVER_SESSION_PROPERTY, v13, a4, v15);
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_Dd(1049, 31, WPP_77b773efe445301db38c0738c64be0c3_Traceguids, (unsigned int)v15, a4);
  if ( v15 >= 0 && v11 )
    UlFlushCacheByServerSession(v14);
LABEL_49:
  v34 = 0;
  v35 = 0;
  if ( v14 )
  {
    v30 = _InterlockedDecrement((volatile signed __int32 *)(v14 + 4));
    if ( UxDebugCheckRefcount && v30 <= -1 )
      UlBugCheckEx(3u, v14 + 4, 0xBu, v30);
    if ( !v30 )
      UlFreeServerSession((PVOID)v14);
  }
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(*(_QWORD *)(a2 + 56) + 1368LL));
  KeLeaveCriticalRegion();
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1033, 32, WPP_77b773efe445301db38c0738c64be0c3_Traceguids, (unsigned int)v15);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400d7828  push    rbp
0x1400d782a  push    rbx
0x1400d782b  push    rsi
0x1400d782c  push    rdi
0x1400d782d  push    r12
0x1400d782f  push    r13
0x1400d7831  push    r14
0x1400d7833  push    r15
0x1400d7835  lea     rbp, [rsp-0Fh]
0x1400d783a  sub     rsp, 0D8h
0x1400d7841  mov     rax, cs:__security_cookie
0x1400d7848  xor     rax, rsp
0x1400d784b  mov     [rbp+47h+var_50], rax
0x1400d784f  mov     rsi, [rbp+47h+arg_20]
0x1400d7853  xor     eax, eax
0x1400d7855  mov     rdi, r8
0x1400d7858  mov     [rbp+47h+var_60], rax
0x1400d785c  mov     r13, rdx
0x1400d785f  mov     [rbp+47h+var_58], eax
0x1400d7862  mov     r15, rcx
0x1400d7865  xor     edx, edx; Val
0x1400d7867  lea     r8d, [rax+50h]; Size
0x1400d786b  mov     r12d, r9d
0x1400d786e  lea     rcx, [rbp+47h+var_B0]; void *
0x1400d7872  call    memset
0x1400d7877  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400d787e  jz      short loc_1400D78B4
0x1400d7880  mov     eax, [rbp+47h+arg_28]
0x1400d7883  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d788a  mov     [rsp+110h+var_D0], eax
0x1400d788e  mov     edx, 1Eh
0x1400d7893  mov     [rsp+110h+var_D8], rsi
0x1400d7898  mov     ecx, 409h
0x1400d789d  mov     [rsp+110h+var_E0], r12d
0x1400d78a2  mov     r9, r15
0x1400d78a5  mov     qword ptr [rsp+110h+var_E8], rdi
0x1400d78aa  mov     [rsp+110h+Irp], r13
0x1400d78af  call    WPP_SF_qqiLqL
0x1400d78b4  mov     rbx, [r13+38h]
0x1400d78b8  call    cs:__imp_KeEnterCriticalRegion
0x1400d78bf  nop     dword ptr [rax+rax+00h]
0x1400d78c4  mov     rcx, [rbx+558h]
0x1400d78cb  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400d78d2  nop     dword ptr [rax+rax+00h]
0x1400d78d7  mov     r14d, 1
0x1400d78dd  mov     [rsp+110h+Irp], r13
0x1400d78e2  mov     edx, r14d
0x1400d78e5  lea     r9, UlValidateServerSession
0x1400d78ec  lea     r8, UlReferenceServerSession
0x1400d78f3  mov     rcx, rdi
0x1400d78f6  call    UxGetObjectFromOpaqueId
0x1400d78fb  mov     rdi, rax
0x1400d78fe  test    rax, rax
0x1400d7901  jnz     short loc_1400D790D
0x1400d7903  mov     ebx, 0C000000Dh
0x1400d7908  jmp     loc_1400D7BBB
0x1400d790d  cmp     r14w, [rax+10h]
0x1400d7912  jnz     short loc_1400D7926
0x1400d7914  xor     eax, eax
0x1400d7916  cmp     ax, [rdi+12h]
0x1400d791a  jnz     short loc_1400D7926
0x1400d791c  mov     ebx, 0C00000BBh
0x1400d7921  jmp     loc_1400D7BBB
0x1400d7926  xor     ebx, ebx
0x1400d7928  mov     ecx, r12d
0x1400d792b  test    r12d, r12d
0x1400d792e  jz      loc_1400D7A5C
0x1400d7934  sub     ecx, r14d
0x1400d7937  jz      loc_1400D7A42
0x1400d793d  sub     ecx, r14d
0x1400d7940  jz      loc_1400D7A09
0x1400d7946  sub     ecx, r14d
0x1400d7949  jz      loc_1400D79D4
0x1400d794f  sub     ecx, 2
0x1400d7952  jz      short loc_1400D79AF
0x1400d7954  sub     ecx, 3
0x1400d7957  jz      loc_1400D7A5C
0x1400d795d  sub     ecx, r14d
0x1400d7960  jz      short loc_1400D7999
0x1400d7962  cmp     ecx, r14d
0x1400d7965  jz      short loc_1400D7971
0x1400d7967  mov     ebx, 0C000000Dh
0x1400d796c  jmp     loc_1400D7B5C
0x1400d7971  mov     al, [r15+40h]
0x1400d7975  lea     r9, [rdi+178h]; int
0x1400d797c  mov     rcx, [r13+38h]; int
0x1400d7980  xor     r8d, r8d; int
0x1400d7983  mov     [rsp+110h+var_E8], al; char
0x1400d7987  mov     rdx, rsi; int
0x1400d798a  mov     [rsp+110h+Irp], r15; Irp
0x1400d798f  call    UlCaptureChannelBindConfig
0x1400d7994  jmp     loc_1400D7B51
0x1400d7999  mov     rax, [rsi]
0x1400d799c  test    r14b, al
0x1400d799f  jnz     short loc_1400D79A3
0x1400d79a1  xor     eax, eax
0x1400d79a3  mov     [rdi+11Ch], rax
0x1400d79aa  jmp     loc_1400D7B5C
0x1400d79af  mov     rax, [rsi]
0x1400d79b2  mov     rcx, rax
0x1400d79b5  shr     rcx, 20h
0x1400d79b9  cmp     ecx, r14d
0x1400d79bc  ja      short loc_1400D7967
0x1400d79be  cmp     [rdi+60h], ecx
0x1400d79c1  jz      short loc_1400D79CC
0x1400d79c3  mov     [rdi+5Ch], rax
0x1400d79c7  jmp     loc_1400D7B5C
0x1400d79cc  xor     r14b, r14b
0x1400d79cf  jmp     loc_1400D7B5C
0x1400d79d4  mov     eax, [rsi]
0x1400d79d6  movups  xmm0, xmmword ptr [rsi+4]
0x1400d79da  test    r14b, al
0x1400d79dd  jz      short loc_1400D79F2
0x1400d79df  mov     [rdi+108h], eax
0x1400d79e5  movdqu  xmmword ptr [rdi+10Ch], xmm0
0x1400d79ed  jmp     loc_1400D7B5C
0x1400d79f2  xorps   xmm0, xmm0
0x1400d79f5  xor     eax, eax
0x1400d79f7  movups  xmmword ptr [rdi+108h], xmm0
0x1400d79fe  mov     [rdi+118h], eax
0x1400d7a04  jmp     loc_1400D7B5C
0x1400d7a09  mov     r8d, [rbp+47h+arg_28]
0x1400d7a0d  lea     r9, [rbp+47h+var_60]
0x1400d7a11  mov     rdx, rsi
0x1400d7a14  mov     rcx, r15; Irp
0x1400d7a17  call    UlCaptureQosParameter
0x1400d7a1c  mov     ebx, eax
0x1400d7a1e  test    eax, eax
0x1400d7a20  js      loc_1400D7BBB
0x1400d7a26  cmp     dword ptr [rbp+47h+var_60], 0
0x1400d7a2a  jnz     loc_1400D7903
0x1400d7a30  lea     rcx, [rdi+68h]
0x1400d7a34  lea     rdx, [rbp+47h+var_60+4]
0x1400d7a38  call    UlQosConfigureFlowCharacteristics
0x1400d7a3d  jmp     loc_1400D7B51
0x1400d7a42  lea     rcx, [rdi+80h]
0x1400d7a49  mov     r9, r15
0x1400d7a4c  mov     r8, rsi
0x1400d7a4f  mov     rdx, rdi
0x1400d7a52  call    UlConfigLogging
0x1400d7a57  jmp     loc_1400D7B51
0x1400d7a5c  mov     rcx, r15; Irp
0x1400d7a5f  call    cs:__imp_IoIs32bitProcess
0x1400d7a66  nop     dword ptr [rax+rax+00h]
0x1400d7a6b  mov     ecx, [rsi]
0x1400d7a6d  mov     r9b, [rsi+8]
0x1400d7a71  mov     r10b, [rsi+9]
0x1400d7a75  mov     r11b, [rsi+0Ah]
0x1400d7a79  mov     r8d, [rsi+4]
0x1400d7a7d  movzx   edx, byte ptr [rsi+0Bh]
0x1400d7a81  mov     [rbp+47h+var_A8], r9b
0x1400d7a85  mov     [rbp+47h+var_A7], r10b
0x1400d7a89  mov     [rbp+47h+var_A6], r11b
0x1400d7a8d  mov     dword ptr [rbp+47h+var_C0], ecx
0x1400d7a90  mov     [rbp+47h+var_B0], ecx
0x1400d7a93  mov     [rbp+47h+var_AC], r8d
0x1400d7a97  test    al, al
0x1400d7a99  jz      short loc_1400D7AC6
0x1400d7a9b  mov     eax, [rsi+18h]
0x1400d7a9e  mov     [rbp+47h+var_88], rax
0x1400d7aa2  movzx   eax, word ptr [rsi+14h]
0x1400d7aa6  mov     [rbp+47h+var_90], ax
0x1400d7aaa  mov     eax, [rsi+10h]
0x1400d7aad  mov     [rbp+47h+var_98], rax
0x1400d7ab1  movzx   eax, word ptr [rsi+0Ch]
0x1400d7ab5  mov     [rbp+47h+var_A0], ax
0x1400d7ab9  mov     eax, [rsi+20h]
0x1400d7abc  mov     [rbp+47h+var_78], rax
0x1400d7ac0  movzx   eax, word ptr [rsi+1Ch]
0x1400d7ac4  jmp     short loc_1400D7AF5
0x1400d7ac6  mov     rax, [rsi+28h]
0x1400d7aca  mov     [rbp+47h+var_88], rax
0x1400d7ace  movzx   eax, word ptr [rsi+20h]
0x1400d7ad2  mov     [rbp+47h+var_90], ax
0x1400d7ad6  mov     rax, [rsi+18h]
0x1400d7ada  mov     [rbp+47h+var_98], rax
0x1400d7ade  movzx   eax, word ptr [rsi+10h]
0x1400d7ae2  mov     [rbp+47h+var_A0], ax
0x1400d7ae6  mov     rax, [rsi+38h]
0x1400d7aea  mov     [rbp+47h+var_78], rax
0x1400d7aee  movzx   eax, word ptr [rsi+30h]
0x1400d7af2  mov     dword ptr [rbp+47h+var_C0], ecx
0x1400d7af5  mov     rsi, [r13+38h]
0x1400d7af9  mov     ecx, edx
0x1400d7afb  mov     [rbp+47h+var_80], ax
0x1400d7aff  lea     rdx, [rbp+47h+var_B0]
0x1400d7b03  xor     eax, eax
0x1400d7b05  xorps   xmm0, xmm0
0x1400d7b08  cmp     r12d, 8
0x1400d7b0c  movdqa  [rbp+47h+var_70], xmm0
0x1400d7b11  cmovnz  ecx, eax
0x1400d7b14  mov     [rbp+47h+var_A5], cl
0x1400d7b17  mov     rcx, rsi
0x1400d7b1a  call    UlVerifyAuthConfig
0x1400d7b1f  mov     ebx, eax
0x1400d7b21  test    eax, eax
0x1400d7b23  js      short loc_1400D7B5C
0x1400d7b25  lea     rcx, [rdi+128h]
0x1400d7b2c  test    [rbp+47h+var_C0], r14b
0x1400d7b30  jz      short loc_1400D7B55
0x1400d7b32  mov     al, [r15+40h]
0x1400d7b36  lea     r8, [rbp+47h+var_B0]
0x1400d7b3a  mov     rdx, rcx
0x1400d7b3d  mov     [rsp+110h+var_E8], al
0x1400d7b41  xor     r9d, r9d
0x1400d7b44  mov     byte ptr [rsp+110h+Irp], 0
0x1400d7b49  mov     rcx, rsi
0x1400d7b4c  call    UlCopyAuthConfig
0x1400d7b51  mov     ebx, eax
0x1400d7b53  jmp     short loc_1400D7B5C
0x1400d7b55  xor     edx, edx
0x1400d7b57  call    UlFreeAuthConfig
0x1400d7b5c  mov     rcx, [r13+38h]
0x1400d7b60  test    byte ptr [rcx+6E1h], 20h
0x1400d7b67  jz      short loc_1400D7B83
0x1400d7b69  add     rcx, 698h
0x1400d7b70  mov     dword ptr [rsp+110h+Irp], ebx
0x1400d7b74  mov     r9d, r12d
0x1400d7b77  lea     rdx, HTTP_EVENT_SET_SERVER_SESSION_PROPERTY
0x1400d7b7e  call    McTemplateK0qq_EtwWriteTransfer
0x1400d7b83  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x1400d7b8a  jz      short loc_1400D7BAA
0x1400d7b8c  mov     edx, 1Fh
0x1400d7b91  mov     dword ptr [rsp+110h+Irp], r12d
0x1400d7b96  mov     ecx, 419h
0x1400d7b9b  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d7ba2  mov     r9d, ebx
0x1400d7ba5  call    WPP_SF_Dd
0x1400d7baa  test    ebx, ebx
0x1400d7bac  js      short loc_1400D7BBB
0x1400d7bae  test    r14b, r14b
0x1400d7bb1  jz      short loc_1400D7BBB
0x1400d7bb3  mov     rcx, rdi
0x1400d7bb6  call    UlFlushCacheByServerSession
0x1400d7bbb  xor     eax, eax
0x1400d7bbd  mov     [rbp+47h+var_60], rax
0x1400d7bc1  mov     [rbp+47h+var_58], eax
0x1400d7bc4  test    rdi, rdi
0x1400d7bc7  jz      short loc_1400D7C02
0x1400d7bc9  lea     rdx, [rdi+4]; BugCheckParameter2
0x1400d7bcd  or      eax, 0FFFFFFFFh
0x1400d7bd0  lock xadd [rdx], eax
0x1400d7bd4  dec     eax
0x1400d7bd6  cmp     cs:UxDebugCheckRefcount, 0
0x1400d7bdd  jz      short loc_1400D7BF6
0x1400d7bdf  cmp     eax, 0FFFFFFFFh
0x1400d7be2  jg      short loc_1400D7BF6
0x1400d7be4  mov     ecx, 3; BugCheckParameter1
0x1400d7be9  movsxd  r9, eax; BugCheckParameter4
0x1400d7bec  lea     r8d, [rcx+8]; BugCheckParameter3
0x1400d7bf0  call    UlBugCheckEx
0x1400d7bf6  test    eax, eax
0x1400d7bf8  jnz     short loc_1400D7C02
0x1400d7bfa  mov     rcx, rdi; P
0x1400d7bfd  call    UlFreeServerSession
0x1400d7c02  mov     rcx, [r13+38h]
0x1400d7c06  mov     rcx, [rcx+558h]
0x1400d7c0d  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400d7c14  nop     dword ptr [rax+rax+00h]
0x1400d7c19  call    cs:__imp_KeLeaveCriticalRegion
0x1400d7c20  nop     dword ptr [rax+rax+00h]
0x1400d7c25  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400d7c2c  jz      short loc_1400D7C47
0x1400d7c2e  mov     edx, 20h ; ' '
0x1400d7c33  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d7c3a  mov     ecx, 409h
0x1400d7c3f  mov     r9d, ebx
0x1400d7c42  call    WPP_SF_d
0x1400d7c47  mov     eax, ebx
0x1400d7c49  mov     rcx, [rbp+47h+var_50]
0x1400d7c4d  xor     rcx, rsp; StackCookie
0x1400d7c50  call    __security_check_cookie
0x1400d7c55  add     rsp, 0D8h
0x1400d7c5c  pop     r15
0x1400d7c5e  pop     r14
0x1400d7c60  pop     r13
0x1400d7c62  pop     r12
0x1400d7c64  pop     rdi
0x1400d7c65  pop     rsi
0x1400d7c66  pop     rbx
0x1400d7c67  pop     rbp
0x1400d7c68  retn
```
