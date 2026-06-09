# UlSetServerSessionProperty

- ea: `0x1400d78d8`
- end: `0x1400d7d1a`
- name: `UlSetServerSessionProperty`
- size: `1090`
- prototype: `__int64 __usercall@<rax>(PIRP Irp@<rcx>, int, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x1400f3150`

## callees

- `0x14000a350`
- `0x1400193f8`
- `0x140074488`
- `0x140086910`
- `0x1400869e0`
- `0x1400cba04`
- `0x1400d29f8`
- `0x1400d742c`
- `0x1400d78d8`
- `0x1400eeb64`
- `0x1400fd210`
- `0x140142d04`
- `0x140146b48`
- `0x140167700`
- `0x140167b40`
- `0x1401c9510`
- `0x1401d9e44`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1400d7b0f`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d7b0f`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d7cbd`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400d7cbd`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d797b`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400d797b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7cc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d7cc9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7968`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d7968`

## pseudocode

```c
__int64 __fastcall UlSetServerSessionProperty(PIRP Irp, __int64 a2, __int64 a3, unsigned int a4, __int64 *a5, int a6)
{
  __int64 v10; // rbx
  char v11; // r14
  __int64 ObjectFromOpaqueId; // rax
  __int64 v13; // r8
  __int64 v14; // rdi
  int v15; // ebx
  int v16; // eax
  __int64 v17; // rax
  unsigned __int64 v18; // rcx
  __int128 v19; // xmm0
  BOOLEAN v20; // al
  int v21; // ecx
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
      v16 = UlConfigLogging(ObjectFromOpaqueId + 128, ObjectFromOpaqueId, (int *)a5, Irp);
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
      v19 = *(_OWORD *)((char *)a5 + 4);
      if ( (*(_DWORD *)a5 & 1) != 0 )
      {
        *(_DWORD *)(ObjectFromOpaqueId + 264) = *(_DWORD *)a5;
        *(_OWORD *)(ObjectFromOpaqueId + 268) = v19;
      }
      else
      {
        *(_OWORD *)(ObjectFromOpaqueId + 264) = 0;
        *(_DWORD *)(ObjectFromOpaqueId + 280) = 0;
      }
      goto LABEL_42;
    case 5u:
      v18 = HIDWORD(*a5);
      if ( (unsigned int)v18 <= 1 )
      {
        if ( *(_DWORD *)(ObjectFromOpaqueId + 96) == (_DWORD)v18 )
          v11 = 0;
        else
          *(_QWORD *)(ObjectFromOpaqueId + 92) = *a5;
        goto LABEL_42;
      }
      break;
    case 8u:
LABEL_32:
      v20 = IoIs32bitProcess(Irp);
      v21 = *(_DWORD *)a5;
      v22 = *((_BYTE *)a5 + 9);
      v23 = *((_BYTE *)a5 + 10);
      v24 = *((_DWORD *)a5 + 1);
      v25 = *((_BYTE *)a5 + 11);
      BYTE8(v33[0]) = *((_BYTE *)a5 + 8);
      BYTE9(v33[0]) = v22;
      BYTE10(v33[0]) = v23;
      v32 = v21;
      *(_QWORD *)&v33[0] = __PAIR64__(v24, v21);
      if ( v20 )
      {
        *((_QWORD *)&v33[2] + 1) = *((unsigned int *)a5 + 6);
        LOWORD(v33[2]) = *((_WORD *)a5 + 10);
        *((_QWORD *)&v33[1] + 1) = *((unsigned int *)a5 + 4);
        LOWORD(v33[1]) = *((_WORD *)a5 + 6);
        *((_QWORD *)&v33[3] + 1) = *((unsigned int *)a5 + 8);
        v26 = *((_WORD *)a5 + 14);
      }
      else
      {
        *((_QWORD *)&v33[2] + 1) = a5[5];
        LOWORD(v33[2]) = *((_WORD *)a5 + 16);
        *((_QWORD *)&v33[1] + 1) = a5[3];
        LOWORD(v33[1]) = *((_WORD *)a5 + 8);
        *((_QWORD *)&v33[3] + 1) = a5[7];
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
      v17 = *a5;
      if ( (*a5 & 1) == 0 )
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
0x1400d78d8  push    rbp
0x1400d78da  push    rbx
0x1400d78db  push    rsi
0x1400d78dc  push    rdi
0x1400d78dd  push    r12
0x1400d78df  push    r13
0x1400d78e1  push    r14
0x1400d78e3  push    r15
0x1400d78e5  lea     rbp, [rsp-0Fh]
0x1400d78ea  sub     rsp, 0D8h
0x1400d78f1  mov     rax, cs:__security_cookie
0x1400d78f8  xor     rax, rsp
0x1400d78fb  mov     [rbp+47h+var_50], rax
0x1400d78ff  mov     rsi, [rbp+47h+arg_20]
0x1400d7903  xor     eax, eax
0x1400d7905  mov     rdi, r8
0x1400d7908  mov     [rbp+47h+var_60], rax
0x1400d790c  mov     r13, rdx
0x1400d790f  mov     [rbp+47h+var_58], eax
0x1400d7912  mov     r15, rcx
0x1400d7915  xor     edx, edx; Val
0x1400d7917  lea     r8d, [rax+50h]; Size
0x1400d791b  mov     r12d, r9d
0x1400d791e  lea     rcx, [rbp+47h+var_B0]; void *
0x1400d7922  call    memset
0x1400d7927  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400d792e  jz      short loc_1400D7964
0x1400d7930  mov     eax, [rbp+47h+arg_28]
0x1400d7933  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d793a  mov     [rsp+110h+var_D0], eax
0x1400d793e  mov     edx, 1Eh
0x1400d7943  mov     [rsp+110h+var_D8], rsi
0x1400d7948  mov     ecx, 409h
0x1400d794d  mov     [rsp+110h+var_E0], r12d
0x1400d7952  mov     r9, r15
0x1400d7955  mov     qword ptr [rsp+110h+var_E8], rdi
0x1400d795a  mov     [rsp+110h+Irp], r13
0x1400d795f  call    WPP_SF_qqiLqL
0x1400d7964  mov     rbx, [r13+38h]
0x1400d7968  call    cs:__imp_KeEnterCriticalRegion
0x1400d796f  nop     dword ptr [rax+rax+00h]
0x1400d7974  mov     rcx, [rbx+558h]
0x1400d797b  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400d7982  nop     dword ptr [rax+rax+00h]
0x1400d7987  mov     r14d, 1
0x1400d798d  mov     [rsp+110h+Irp], r13
0x1400d7992  mov     edx, r14d
0x1400d7995  lea     r9, UlValidateServerSession
0x1400d799c  lea     r8, UlReferenceServerSession
0x1400d79a3  mov     rcx, rdi
0x1400d79a6  call    UxGetObjectFromOpaqueId
0x1400d79ab  mov     rdi, rax
0x1400d79ae  test    rax, rax
0x1400d79b1  jnz     short loc_1400D79BD
0x1400d79b3  mov     ebx, 0C000000Dh
0x1400d79b8  jmp     loc_1400D7C6B
0x1400d79bd  cmp     r14w, [rax+10h]
0x1400d79c2  jnz     short loc_1400D79D6
0x1400d79c4  xor     eax, eax
0x1400d79c6  cmp     ax, [rdi+12h]
0x1400d79ca  jnz     short loc_1400D79D6
0x1400d79cc  mov     ebx, 0C00000BBh
0x1400d79d1  jmp     loc_1400D7C6B
0x1400d79d6  xor     ebx, ebx
0x1400d79d8  mov     ecx, r12d
0x1400d79db  test    r12d, r12d
0x1400d79de  jz      loc_1400D7B0C
0x1400d79e4  sub     ecx, r14d
0x1400d79e7  jz      loc_1400D7AF2
0x1400d79ed  sub     ecx, r14d
0x1400d79f0  jz      loc_1400D7AB9
0x1400d79f6  sub     ecx, r14d
0x1400d79f9  jz      loc_1400D7A84
0x1400d79ff  sub     ecx, 2
0x1400d7a02  jz      short loc_1400D7A5F
0x1400d7a04  sub     ecx, 3
0x1400d7a07  jz      loc_1400D7B0C
0x1400d7a0d  sub     ecx, r14d
0x1400d7a10  jz      short loc_1400D7A49
0x1400d7a12  cmp     ecx, r14d
0x1400d7a15  jz      short loc_1400D7A21
0x1400d7a17  mov     ebx, 0C000000Dh
0x1400d7a1c  jmp     loc_1400D7C0C
0x1400d7a21  mov     al, [r15+40h]
0x1400d7a25  lea     r9, [rdi+178h]; int
0x1400d7a2c  mov     rcx, [r13+38h]; int
0x1400d7a30  xor     r8d, r8d; int
0x1400d7a33  mov     [rsp+110h+var_E8], al; char
0x1400d7a37  mov     rdx, rsi; int
0x1400d7a3a  mov     [rsp+110h+Irp], r15; Irp
0x1400d7a3f  call    UlCaptureChannelBindConfig
0x1400d7a44  jmp     loc_1400D7C01
0x1400d7a49  mov     rax, [rsi]
0x1400d7a4c  test    r14b, al
0x1400d7a4f  jnz     short loc_1400D7A53
0x1400d7a51  xor     eax, eax
0x1400d7a53  mov     [rdi+11Ch], rax
0x1400d7a5a  jmp     loc_1400D7C0C
0x1400d7a5f  mov     rax, [rsi]
0x1400d7a62  mov     rcx, rax
0x1400d7a65  shr     rcx, 20h
0x1400d7a69  cmp     ecx, r14d
0x1400d7a6c  ja      short loc_1400D7A17
0x1400d7a6e  cmp     [rdi+60h], ecx
0x1400d7a71  jz      short loc_1400D7A7C
0x1400d7a73  mov     [rdi+5Ch], rax
0x1400d7a77  jmp     loc_1400D7C0C
0x1400d7a7c  xor     r14b, r14b
0x1400d7a7f  jmp     loc_1400D7C0C
0x1400d7a84  mov     eax, [rsi]
0x1400d7a86  movups  xmm0, xmmword ptr [rsi+4]
0x1400d7a8a  test    r14b, al
0x1400d7a8d  jz      short loc_1400D7AA2
0x1400d7a8f  mov     [rdi+108h], eax
0x1400d7a95  movdqu  xmmword ptr [rdi+10Ch], xmm0
0x1400d7a9d  jmp     loc_1400D7C0C
0x1400d7aa2  xorps   xmm0, xmm0
0x1400d7aa5  xor     eax, eax
0x1400d7aa7  movups  xmmword ptr [rdi+108h], xmm0
0x1400d7aae  mov     [rdi+118h], eax
0x1400d7ab4  jmp     loc_1400D7C0C
0x1400d7ab9  mov     r8d, [rbp+47h+arg_28]
0x1400d7abd  lea     r9, [rbp+47h+var_60]
0x1400d7ac1  mov     rdx, rsi
0x1400d7ac4  mov     rcx, r15; Irp
0x1400d7ac7  call    UlCaptureQosParameter
0x1400d7acc  mov     ebx, eax
0x1400d7ace  test    eax, eax
0x1400d7ad0  js      loc_1400D7C6B
0x1400d7ad6  cmp     dword ptr [rbp+47h+var_60], 0
0x1400d7ada  jnz     loc_1400D79B3
0x1400d7ae0  lea     rcx, [rdi+68h]
0x1400d7ae4  lea     rdx, [rbp+47h+var_60+4]
0x1400d7ae8  call    UlQosConfigureFlowCharacteristics
0x1400d7aed  jmp     loc_1400D7C01
0x1400d7af2  lea     rcx, [rdi+80h]
0x1400d7af9  mov     r9, r15
0x1400d7afc  mov     r8, rsi
0x1400d7aff  mov     rdx, rdi
0x1400d7b02  call    UlConfigLogging
0x1400d7b07  jmp     loc_1400D7C01
0x1400d7b0c  mov     rcx, r15; Irp
0x1400d7b0f  call    cs:__imp_IoIs32bitProcess
0x1400d7b16  nop     dword ptr [rax+rax+00h]
0x1400d7b1b  mov     ecx, [rsi]
0x1400d7b1d  mov     r9b, [rsi+8]
0x1400d7b21  mov     r10b, [rsi+9]
0x1400d7b25  mov     r11b, [rsi+0Ah]
0x1400d7b29  mov     r8d, [rsi+4]
0x1400d7b2d  movzx   edx, byte ptr [rsi+0Bh]
0x1400d7b31  mov     [rbp+47h+var_A8], r9b
0x1400d7b35  mov     [rbp+47h+var_A7], r10b
0x1400d7b39  mov     [rbp+47h+var_A6], r11b
0x1400d7b3d  mov     dword ptr [rbp+47h+var_C0], ecx
0x1400d7b40  mov     [rbp+47h+var_B0], ecx
0x1400d7b43  mov     [rbp+47h+var_AC], r8d
0x1400d7b47  test    al, al
0x1400d7b49  jz      short loc_1400D7B76
0x1400d7b4b  mov     eax, [rsi+18h]
0x1400d7b4e  mov     [rbp+47h+var_88], rax
0x1400d7b52  movzx   eax, word ptr [rsi+14h]
0x1400d7b56  mov     [rbp+47h+var_90], ax
0x1400d7b5a  mov     eax, [rsi+10h]
0x1400d7b5d  mov     [rbp+47h+var_98], rax
0x1400d7b61  movzx   eax, word ptr [rsi+0Ch]
0x1400d7b65  mov     [rbp+47h+var_A0], ax
0x1400d7b69  mov     eax, [rsi+20h]
0x1400d7b6c  mov     [rbp+47h+var_78], rax
0x1400d7b70  movzx   eax, word ptr [rsi+1Ch]
0x1400d7b74  jmp     short loc_1400D7BA5
0x1400d7b76  mov     rax, [rsi+28h]
0x1400d7b7a  mov     [rbp+47h+var_88], rax
0x1400d7b7e  movzx   eax, word ptr [rsi+20h]
0x1400d7b82  mov     [rbp+47h+var_90], ax
0x1400d7b86  mov     rax, [rsi+18h]
0x1400d7b8a  mov     [rbp+47h+var_98], rax
0x1400d7b8e  movzx   eax, word ptr [rsi+10h]
0x1400d7b92  mov     [rbp+47h+var_A0], ax
0x1400d7b96  mov     rax, [rsi+38h]
0x1400d7b9a  mov     [rbp+47h+var_78], rax
0x1400d7b9e  movzx   eax, word ptr [rsi+30h]
0x1400d7ba2  mov     dword ptr [rbp+47h+var_C0], ecx
0x1400d7ba5  mov     rsi, [r13+38h]
0x1400d7ba9  mov     ecx, edx
0x1400d7bab  mov     [rbp+47h+var_80], ax
0x1400d7baf  lea     rdx, [rbp+47h+var_B0]
0x1400d7bb3  xor     eax, eax
0x1400d7bb5  xorps   xmm0, xmm0
0x1400d7bb8  cmp     r12d, 8
0x1400d7bbc  movdqa  [rbp+47h+var_70], xmm0
0x1400d7bc1  cmovnz  ecx, eax
0x1400d7bc4  mov     [rbp+47h+var_A5], cl
0x1400d7bc7  mov     rcx, rsi
0x1400d7bca  call    UlVerifyAuthConfig
0x1400d7bcf  mov     ebx, eax
0x1400d7bd1  test    eax, eax
0x1400d7bd3  js      short loc_1400D7C0C
0x1400d7bd5  lea     rcx, [rdi+128h]
0x1400d7bdc  test    [rbp+47h+var_C0], r14b
0x1400d7be0  jz      short loc_1400D7C05
0x1400d7be2  mov     al, [r15+40h]
0x1400d7be6  lea     r8, [rbp+47h+var_B0]
0x1400d7bea  mov     rdx, rcx
0x1400d7bed  mov     [rsp+110h+var_E8], al
0x1400d7bf1  xor     r9d, r9d
0x1400d7bf4  mov     byte ptr [rsp+110h+Irp], 0
0x1400d7bf9  mov     rcx, rsi
0x1400d7bfc  call    UlCopyAuthConfig
0x1400d7c01  mov     ebx, eax
0x1400d7c03  jmp     short loc_1400D7C0C
0x1400d7c05  xor     edx, edx
0x1400d7c07  call    UlFreeAuthConfig
0x1400d7c0c  mov     rcx, [r13+38h]
0x1400d7c10  test    byte ptr [rcx+6E1h], 20h
0x1400d7c17  jz      short loc_1400D7C33
0x1400d7c19  add     rcx, 698h
0x1400d7c20  mov     dword ptr [rsp+110h+Irp], ebx
0x1400d7c24  mov     r9d, r12d
0x1400d7c27  lea     rdx, HTTP_EVENT_SET_SERVER_SESSION_PROPERTY
0x1400d7c2e  call    McTemplateK0qq_EtwWriteTransfer
0x1400d7c33  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x1400d7c3a  jz      short loc_1400D7C5A
0x1400d7c3c  mov     edx, 1Fh
0x1400d7c41  mov     dword ptr [rsp+110h+Irp], r12d
0x1400d7c46  mov     ecx, 419h
0x1400d7c4b  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d7c52  mov     r9d, ebx
0x1400d7c55  call    WPP_SF_Dd
0x1400d7c5a  test    ebx, ebx
0x1400d7c5c  js      short loc_1400D7C6B
0x1400d7c5e  test    r14b, r14b
0x1400d7c61  jz      short loc_1400D7C6B
0x1400d7c63  mov     rcx, rdi
0x1400d7c66  call    UlFlushCacheByServerSession
0x1400d7c6b  xor     eax, eax
0x1400d7c6d  mov     [rbp+47h+var_60], rax
0x1400d7c71  mov     [rbp+47h+var_58], eax
0x1400d7c74  test    rdi, rdi
0x1400d7c77  jz      short loc_1400D7CB2
0x1400d7c79  lea     rdx, [rdi+4]; BugCheckParameter2
0x1400d7c7d  or      eax, 0FFFFFFFFh
0x1400d7c80  lock xadd [rdx], eax
0x1400d7c84  dec     eax
0x1400d7c86  cmp     cs:UxDebugCheckRefcount, 0
0x1400d7c8d  jz      short loc_1400D7CA6
0x1400d7c8f  cmp     eax, 0FFFFFFFFh
0x1400d7c92  jg      short loc_1400D7CA6
0x1400d7c94  mov     ecx, 3; BugCheckParameter1
0x1400d7c99  movsxd  r9, eax; BugCheckParameter4
0x1400d7c9c  lea     r8d, [rcx+8]; BugCheckParameter3
0x1400d7ca0  call    UlBugCheckEx
0x1400d7ca6  test    eax, eax
0x1400d7ca8  jnz     short loc_1400D7CB2
0x1400d7caa  mov     rcx, rdi; P
0x1400d7cad  call    UlFreeServerSession
0x1400d7cb2  mov     rcx, [r13+38h]
0x1400d7cb6  mov     rcx, [rcx+558h]
0x1400d7cbd  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400d7cc4  nop     dword ptr [rax+rax+00h]
0x1400d7cc9  call    cs:__imp_KeLeaveCriticalRegion
0x1400d7cd0  nop     dword ptr [rax+rax+00h]
0x1400d7cd5  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400d7cdc  jz      short loc_1400D7CF7
0x1400d7cde  mov     edx, 20h ; ' '
0x1400d7ce3  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d7cea  mov     ecx, 409h
0x1400d7cef  mov     r9d, ebx
0x1400d7cf2  call    WPP_SF_d
0x1400d7cf7  mov     eax, ebx
0x1400d7cf9  mov     rcx, [rbp+47h+var_50]
0x1400d7cfd  xor     rcx, rsp; StackCookie
0x1400d7d00  call    __security_check_cookie
0x1400d7d05  add     rsp, 0D8h
0x1400d7d0c  pop     r15
0x1400d7d0e  pop     r14
0x1400d7d10  pop     r13
0x1400d7d12  pop     r12
0x1400d7d14  pop     rdi
0x1400d7d15  pop     rsi
0x1400d7d16  pop     rbx
0x1400d7d17  pop     rbp
0x1400d7d18  retn
```
