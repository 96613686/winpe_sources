# UlSetServerSessionProperty

- ea: `0x1c010ca60`
- end: `0x1c010cea2`
- name: `UlSetServerSessionProperty`
- size: `1090`
- prototype: `__int64 __usercall@<rax>(PIRP Irp@<rcx>, __int64, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1c011ca10`

## callees

- `0x1c0003974`
- `0x1c000b7cc`
- `0x1c001a4b0`
- `0x1c001b900`
- `0x1c00295a4`
- `0x1c00325a8`
- `0x1c008f374`
- `0x1c008f3a8`
- `0x1c009416c`
- `0x1c00a17c0`
- `0x1c00a8364`
- `0x1c00b0160`
- `0x1c0106780`
- `0x1c010ca60`
- `0x1c0118f80`
- `0x1c0138aa4`
- `0x1c013a348`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1c010cca1`
- `ntoskrnl!IoIs32bitProcess` at `0x1c010cca1`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c010ce47`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c010ce47`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c010cb0c`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c010cb0c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010ce53`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010ce53`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c010caf9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c010caf9`

## pseudocode

```c
__int64 __fastcall UlSetServerSessionProperty(PIRP Irp, __int64 a2, __int64 a3, unsigned int a4, __m128i *a5, int a6)
{
  int v10; // edi
  char v11; // r14
  __int64 v12; // rbx
  __int64 ObjectFromOpaqueId; // rbx
  int v14; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  __m128i v17; // xmm0
  __int32 v18; // ecx
  BOOLEAN v19; // al
  int v20; // ecx
  __int8 v21; // r10
  __int8 v22; // r11
  __int32 v23; // r8d
  __int8 v24; // dl
  __int16 v25; // ax
  __int64 v26; // rsi
  __int8 v27; // al
  int v29; // [rsp+20h] [rbp-C9h]
  int v30; // [rsp+40h] [rbp-A9h]
  char v31; // [rsp+40h] [rbp-A9h]
  _OWORD v32[6]; // [rsp+50h] [rbp-99h] BYREF
  __int32 v33; // [rsp+B0h] [rbp-39h]
  __int128 v34; // [rsp+B8h] [rbp-31h] BYREF
  __int64 v35; // [rsp+C8h] [rbp-21h]
  char v36; // [rsp+D0h] [rbp-19h]
  int v37; // [rsp+D1h] [rbp-18h]
  __int16 v38; // [rsp+D5h] [rbp-14h]
  char v39; // [rsp+D7h] [rbp-12h]
  __int64 v40; // [rsp+D8h] [rbp-11h] BYREF
  int v41; // [rsp+E0h] [rbp-9h]

  v40 = 0;
  v30 = a3;
  v41 = 0;
  v10 = 0;
  memset(v32, 0, 0x50u);
  v11 = 1;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qqiLqL(30, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids, Irp, a2, a3, a4, a5, a6);
  v12 = *(_QWORD *)(a2 + 56);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v12 + 1360));
  ObjectFromOpaqueId = UxGetObjectFromOpaqueId(
                         v30,
                         1,
                         (unsigned int)UlReferenceServerSession,
                         (unsigned int)UlValidateServerSession,
                         a2);
  if ( !ObjectFromOpaqueId )
  {
LABEL_4:
    v10 = -1073741811;
    goto LABEL_49;
  }
  if ( *(_WORD *)(ObjectFromOpaqueId + 16) == 1 && !*(_WORD *)(ObjectFromOpaqueId + 18) )
  {
    v10 = -1073741637;
    goto LABEL_49;
  }
  switch ( a4 )
  {
    case 0u:
      goto LABEL_33;
    case 1u:
      v14 = UlConfigLogging(ObjectFromOpaqueId + 128, ObjectFromOpaqueId, a5->m128i_i32, Irp);
      goto LABEL_31;
    case 2u:
      v10 = UlCaptureQosParameter(Irp);
      if ( v10 < 0 )
        goto LABEL_49;
      if ( (_DWORD)v40 )
        goto LABEL_4;
      v14 = UlQosConfigureFlowCharacteristics(ObjectFromOpaqueId + 104, (char *)&v40 + 4);
      goto LABEL_31;
    case 3u:
      v17 = *a5;
      v18 = a5[1].m128i_i32[0];
      v33 = v18;
      v32[5] = v17;
      if ( (_mm_cvtsi128_si32(v17) & 1) != 0 )
      {
        *(__m128i *)(ObjectFromOpaqueId + 264) = v17;
        *(_DWORD *)(ObjectFromOpaqueId + 280) = v18;
      }
      else
      {
        *(_OWORD *)(ObjectFromOpaqueId + 264) = 0;
        *(_DWORD *)(ObjectFromOpaqueId + 280) = 0;
      }
      goto LABEL_42;
    case 5u:
      v16 = HIDWORD(a5->m128i_i64[0]);
      if ( (unsigned int)v16 <= 1 )
      {
        if ( *(_DWORD *)(ObjectFromOpaqueId + 96) == (_DWORD)v16 )
          v11 = 0;
        else
          *(_QWORD *)(ObjectFromOpaqueId + 92) = a5->m128i_i64[0];
        goto LABEL_42;
      }
      break;
    case 8u:
LABEL_33:
      v19 = IoIs32bitProcess(Irp);
      v20 = a5->m128i_i32[0];
      v21 = a5->m128i_i8[9];
      v22 = a5->m128i_i8[10];
      v23 = a5->m128i_i32[1];
      v24 = a5->m128i_i8[11];
      BYTE8(v32[0]) = a5->m128i_i8[8];
      BYTE9(v32[0]) = v21;
      BYTE10(v32[0]) = v22;
      v31 = v20;
      *(_QWORD *)&v32[0] = __PAIR64__(v23, v20);
      if ( v19 )
      {
        *((_QWORD *)&v32[2] + 1) = a5[1].m128i_u32[2];
        LOWORD(v32[2]) = a5[1].m128i_i16[2];
        *((_QWORD *)&v32[1] + 1) = a5[1].m128i_u32[0];
        LOWORD(v32[1]) = a5->m128i_i16[6];
        *((_QWORD *)&v32[3] + 1) = a5[2].m128i_u32[0];
        v25 = a5[1].m128i_i16[6];
      }
      else
      {
        *((_QWORD *)&v32[2] + 1) = a5[2].m128i_i64[1];
        LOWORD(v32[2]) = a5[2].m128i_i16[0];
        *((_QWORD *)&v32[1] + 1) = a5[1].m128i_i64[1];
        LOWORD(v32[1]) = a5[1].m128i_i16[0];
        *((_QWORD *)&v32[3] + 1) = a5[3].m128i_i64[1];
        v25 = a5[3].m128i_i16[0];
        v31 = v20;
      }
      v26 = *(_QWORD *)(a2 + 56);
      LOWORD(v32[3]) = v25;
      v27 = v24;
      v32[4] = 0;
      if ( a4 != 8 )
        v27 = 0;
      BYTE11(v32[0]) = v27;
      v10 = UlVerifyAuthConfig(v26, v32);
      if ( v10 < 0 )
        goto LABEL_42;
      if ( (v31 & 1) == 0 )
      {
        UlFreeAuthConfig(ObjectFromOpaqueId + 296);
        goto LABEL_42;
      }
      v14 = UlCopyAuthConfig(v26, (int)ObjectFromOpaqueId + 296, (unsigned int)v32, 0, Irp->RequestorMode);
      goto LABEL_31;
    case 9u:
      v15 = a5->m128i_i64[0];
      if ( (a5->m128i_i64[0] & 1) == 0 )
        v15 = 0;
      *(_QWORD *)(ObjectFromOpaqueId + 284) = v15;
      goto LABEL_42;
    case 0xAu:
      LOBYTE(v29) = Irp->RequestorMode;
      v14 = UlCaptureChannelBindConfig(*(_QWORD *)(a2 + 56), a5, ObjectFromOpaqueId + 376, Irp, v29);
LABEL_31:
      v10 = v14;
      goto LABEL_42;
  }
  v10 = -1073741811;
LABEL_42:
  if ( *(_BYTE *)(*(_QWORD *)(a2 + 56) + 1568LL) )
  {
    v35 = *(_QWORD *)(a2 + 56);
    v37 = 0;
    v36 = 0;
    v38 = 0;
    v39 = 0;
    v34 = 0;
    McTemplateK0qq_UlEtwWriteEventWrapper(0, HTTP_EVENT_SET_SERVER_SESSION_PROPERTY, &v34, a4, v10);
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
    WPP_SF_DD(31, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids, (unsigned int)v10, a4);
  if ( v10 >= 0 && v11 )
    UlFlushCacheByServerSession(ObjectFromOpaqueId);
LABEL_49:
  v40 = 0;
  v41 = 0;
  if ( ObjectFromOpaqueId
    && _InterlockedExchangeAdd((volatile signed __int32 *)(ObjectFromOpaqueId + 4), 0xFFFFFFFF) == 1 )
  {
    UlFreeServerSession((PVOID)ObjectFromOpaqueId);
  }
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(*(_QWORD *)(a2 + 56) + 1360LL));
  KeLeaveCriticalRegion();
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_D(32, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1c010ca60  push    rbp
0x1c010ca62  push    rbx
0x1c010ca63  push    rsi
0x1c010ca64  push    rdi
0x1c010ca65  push    r12
0x1c010ca67  push    r13
0x1c010ca69  push    r14
0x1c010ca6b  push    r15
0x1c010ca6d  lea     rbp, [rsp-0Fh]
0x1c010ca72  sub     rsp, 0F8h
0x1c010ca79  mov     rax, cs:__security_cookie
0x1c010ca80  xor     rax, rsp
0x1c010ca83  mov     [rbp+47h+var_48], rax
0x1c010ca87  mov     rsi, [rbp+47h+arg_20]
0x1c010ca8b  xor     eax, eax
0x1c010ca8d  mov     rbx, r8
0x1c010ca90  mov     [rbp+47h+var_58], rax
0x1c010ca94  mov     r13, rdx
0x1c010ca97  mov     qword ptr [rsp+130h+var_F0], rbx
0x1c010ca9c  mov     r15, rcx
0x1c010ca9f  mov     [rbp+47h+var_50], eax
0x1c010caa2  lea     r8d, [rax+50h]; Size
0x1c010caa6  xor     edx, edx; Val
0x1c010caa8  lea     rcx, [rsp+130h+var_E0]; void *
0x1c010caad  mov     r12d, r9d
0x1c010cab0  mov     edi, eax
0x1c010cab2  call    memset
0x1c010cab7  mov     r14d, 1
0x1c010cabd  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c010cac7  jz      short loc_1C010CAF5
0x1c010cac9  mov     eax, [rbp+47h+arg_28]
0x1c010cacc  lea     ecx, [r14+1Dh]
0x1c010cad0  mov     [rsp+130h+var_F8], eax
0x1c010cad4  lea     rdx, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids
0x1c010cadb  mov     [rsp+130h+var_100], rsi
0x1c010cae0  mov     r9, r13
0x1c010cae3  mov     [rsp+130h+var_108], r12d
0x1c010cae8  mov     r8, r15
0x1c010caeb  mov     [rsp+130h+var_110], rbx
0x1c010caf0  call    WPP_SF_qqiLqL
0x1c010caf5  mov     rbx, [r13+38h]
0x1c010caf9  call    cs:__imp_KeEnterCriticalRegion
0x1c010cb00  nop     dword ptr [rax+rax+00h]
0x1c010cb05  mov     rcx, [rbx+550h]
0x1c010cb0c  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c010cb13  nop     dword ptr [rax+rax+00h]
0x1c010cb18  mov     rcx, qword ptr [rsp+130h+var_F0]
0x1c010cb1d  lea     r9, UlValidateServerSession
0x1c010cb24  lea     r8, UlReferenceServerSession
0x1c010cb2b  mov     [rsp+130h+var_110], r13
0x1c010cb30  mov     edx, r14d
0x1c010cb33  call    UxGetObjectFromOpaqueId
0x1c010cb38  mov     rbx, rax
0x1c010cb3b  xor     eax, eax
0x1c010cb3d  test    rbx, rbx
0x1c010cb40  jnz     short loc_1C010CB4C
0x1c010cb42  mov     edi, 0C000000Dh
0x1c010cb47  jmp     loc_1C010CE19
0x1c010cb4c  cmp     r14w, [rbx+10h]
0x1c010cb51  jnz     short loc_1C010CB63
0x1c010cb53  cmp     ax, [rbx+12h]
0x1c010cb57  jnz     short loc_1C010CB63
0x1c010cb59  mov     edi, 0C00000BBh
0x1c010cb5e  jmp     loc_1C010CE19
0x1c010cb63  mov     ecx, r12d
0x1c010cb66  test    r12d, r12d
0x1c010cb69  jz      loc_1C010CC9E
0x1c010cb6f  sub     ecx, r14d
0x1c010cb72  jz      loc_1C010CC87
0x1c010cb78  sub     ecx, r14d
0x1c010cb7b  jz      loc_1C010CC4B
0x1c010cb81  sub     ecx, r14d
0x1c010cb84  jz      loc_1C010CC0C
0x1c010cb8a  sub     ecx, 2
0x1c010cb8d  jz      short loc_1C010CBE5
0x1c010cb8f  sub     ecx, 3
0x1c010cb92  jz      loc_1C010CC9E
0x1c010cb98  sub     ecx, r14d
0x1c010cb9b  jz      short loc_1C010CBCF
0x1c010cb9d  cmp     ecx, r14d
0x1c010cba0  jz      short loc_1C010CBAC
0x1c010cba2  mov     edi, 0C000000Dh
0x1c010cba7  jmp     loc_1C010CDA5
0x1c010cbac  mov     al, [r15+40h]
0x1c010cbb0  lea     r8, [rbx+178h]
0x1c010cbb7  mov     rcx, [r13+38h]
0x1c010cbbb  mov     r9, r15
0x1c010cbbe  mov     rdx, rsi
0x1c010cbc1  mov     byte ptr [rsp+130h+var_110], al
0x1c010cbc5  call    UlCaptureChannelBindConfig
0x1c010cbca  jmp     loc_1C010CC80
0x1c010cbcf  mov     rax, [rsi]
0x1c010cbd2  test    r14b, al
0x1c010cbd5  jnz     short loc_1C010CBD9
0x1c010cbd7  xor     eax, eax
0x1c010cbd9  mov     [rbx+11Ch], rax
0x1c010cbe0  jmp     loc_1C010CDA5
0x1c010cbe5  mov     rax, [rsi]
0x1c010cbe8  mov     rcx, rax
0x1c010cbeb  shr     rcx, 20h
0x1c010cbef  cmp     ecx, r14d
0x1c010cbf2  ja      short loc_1C010CBA2
0x1c010cbf4  cmp     [rbx+60h], ecx
0x1c010cbf7  jz      short loc_1C010CC02
0x1c010cbf9  mov     [rbx+5Ch], rax
0x1c010cbfd  jmp     loc_1C010CDA5
0x1c010cc02  xor     eax, eax
0x1c010cc04  mov     r14b, al
0x1c010cc07  jmp     loc_1C010CDA5
0x1c010cc0c  movups  xmm0, xmmword ptr [rsi]
0x1c010cc0f  mov     ecx, [rsi+10h]
0x1c010cc12  mov     [rbp+47h+var_80], ecx
0x1c010cc15  movd    eax, xmm0
0x1c010cc19  movups  [rbp+47h+var_90], xmm0
0x1c010cc1d  test    r14b, al
0x1c010cc20  jz      short loc_1C010CC34
0x1c010cc22  movups  xmmword ptr [rbx+108h], xmm0
0x1c010cc29  mov     [rbx+118h], ecx
0x1c010cc2f  jmp     loc_1C010CDA5
0x1c010cc34  xorps   xmm0, xmm0
0x1c010cc37  xor     eax, eax
0x1c010cc39  movups  xmmword ptr [rbx+108h], xmm0
0x1c010cc40  mov     [rbx+118h], eax
0x1c010cc46  jmp     loc_1C010CDA5
0x1c010cc4b  mov     r8d, [rbp+47h+arg_28]
0x1c010cc4f  lea     r9, [rbp+47h+var_58]
0x1c010cc53  mov     rdx, rsi
0x1c010cc56  mov     rcx, r15; Irp
0x1c010cc59  call    UlCaptureQosParameter
0x1c010cc5e  mov     edi, eax
0x1c010cc60  xor     eax, eax
0x1c010cc62  test    edi, edi
0x1c010cc64  js      loc_1C010CE19
0x1c010cc6a  cmp     dword ptr [rbp+47h+var_58], eax
0x1c010cc6d  jnz     loc_1C010CB42
0x1c010cc73  lea     rcx, [rbx+68h]
0x1c010cc77  lea     rdx, [rbp+47h+var_58+4]
0x1c010cc7b  call    UlQosConfigureFlowCharacteristics
0x1c010cc80  mov     edi, eax
0x1c010cc82  jmp     loc_1C010CDA5
0x1c010cc87  lea     rcx, [rbx+80h]
0x1c010cc8e  mov     r9, r15
0x1c010cc91  mov     r8, rsi
0x1c010cc94  mov     rdx, rbx
0x1c010cc97  call    UlConfigLogging
0x1c010cc9c  jmp     short loc_1C010CC80
0x1c010cc9e  mov     rcx, r15; Irp
0x1c010cca1  call    cs:__imp_IoIs32bitProcess
0x1c010cca8  nop     dword ptr [rax+rax+00h]
0x1c010ccad  mov     ecx, [rsi]
0x1c010ccaf  mov     r9b, [rsi+8]
0x1c010ccb3  mov     r10b, [rsi+9]
0x1c010ccb7  mov     r11b, [rsi+0Ah]
0x1c010ccbb  mov     r8d, [rsi+4]
0x1c010ccbf  movzx   edx, byte ptr [rsi+0Bh]
0x1c010ccc3  mov     [rsp+130h+var_D8], r9b
0x1c010ccc8  mov     [rsp+130h+var_D7], r10b
0x1c010cccd  mov     [rsp+130h+var_D6], r11b
0x1c010ccd2  mov     [rsp+130h+var_F0], ecx
0x1c010ccd6  mov     [rsp+130h+var_E0], ecx
0x1c010ccda  mov     [rsp+130h+var_DC], r8d
0x1c010ccdf  test    al, al
0x1c010cce1  jz      short loc_1C010CD10
0x1c010cce3  mov     eax, [rsi+18h]
0x1c010cce6  mov     [rbp+47h+var_B8], rax
0x1c010ccea  movzx   eax, word ptr [rsi+14h]
0x1c010ccee  mov     [rbp+47h+var_C0], ax
0x1c010ccf2  mov     eax, [rsi+10h]
0x1c010ccf5  mov     [rsp+130h+var_C8], rax
0x1c010ccfa  movzx   eax, word ptr [rsi+0Ch]
0x1c010ccfe  mov     [rsp+130h+var_D0], ax
0x1c010cd03  mov     eax, [rsi+20h]
0x1c010cd06  mov     [rbp+47h+var_A8], rax
0x1c010cd0a  movzx   eax, word ptr [rsi+1Ch]
0x1c010cd0e  jmp     short loc_1C010CD42
0x1c010cd10  mov     rax, [rsi+28h]
0x1c010cd14  mov     [rbp+47h+var_B8], rax
0x1c010cd18  movzx   eax, word ptr [rsi+20h]
0x1c010cd1c  mov     [rbp+47h+var_C0], ax
0x1c010cd20  mov     rax, [rsi+18h]
0x1c010cd24  mov     [rsp+130h+var_C8], rax
0x1c010cd29  movzx   eax, word ptr [rsi+10h]
0x1c010cd2d  mov     [rsp+130h+var_D0], ax
0x1c010cd32  mov     rax, [rsi+38h]
0x1c010cd36  mov     [rbp+47h+var_A8], rax
0x1c010cd3a  movzx   eax, word ptr [rsi+30h]
0x1c010cd3e  mov     [rsp+130h+var_F0], ecx
0x1c010cd42  mov     rsi, [r13+38h]
0x1c010cd46  xorps   xmm0, xmm0
0x1c010cd49  mov     [rbp+47h+var_B0], ax
0x1c010cd4d  cmp     r12d, 8
0x1c010cd51  mov     eax, edx
0x1c010cd53  movdqa  [rbp+47h+var_A0], xmm0
0x1c010cd58  cmovnz  eax, edi
0x1c010cd5b  lea     rdx, [rsp+130h+var_E0]
0x1c010cd60  mov     rcx, rsi
0x1c010cd63  mov     [rsp+130h+var_D5], al
0x1c010cd67  call    UlVerifyAuthConfig
0x1c010cd6c  mov     edi, eax
0x1c010cd6e  test    eax, eax
0x1c010cd70  js      short loc_1C010CDA5
0x1c010cd72  lea     rcx, [rbx+128h]
0x1c010cd79  test    byte ptr [rsp+130h+var_F0], r14b
0x1c010cd7e  jz      short loc_1C010CDA0
0x1c010cd80  mov     al, [r15+40h]
0x1c010cd84  lea     r8, [rsp+130h+var_E0]
0x1c010cd89  mov     rdx, rcx
0x1c010cd8c  mov     byte ptr [rsp+130h+var_110], al
0x1c010cd90  mov     rcx, rsi
0x1c010cd93  xor     r9d, r9d
0x1c010cd96  call    UlCopyAuthConfig
0x1c010cd9b  jmp     loc_1C010CC80
0x1c010cda0  call    UlFreeAuthConfig
0x1c010cda5  mov     rax, [r13+38h]
0x1c010cda9  xor     ecx, ecx
0x1c010cdab  cmp     [rax+620h], cl
0x1c010cdb1  jz      short loc_1C010CDE5
0x1c010cdb3  mov     [rbp+47h+var_68], rax
0x1c010cdb7  lea     r8, [rbp+47h+var_78]
0x1c010cdbb  xor     eax, eax
0x1c010cdbd  mov     [rbp+47h+var_5F], ecx
0x1c010cdc0  xorps   xmm0, xmm0
0x1c010cdc3  mov     [rbp+47h+var_60], al
0x1c010cdc6  mov     r9d, r12d
0x1c010cdc9  mov     [rbp+47h+var_5B], cx
0x1c010cdcd  lea     rdx, HTTP_EVENT_SET_SERVER_SESSION_PROPERTY
0x1c010cdd4  mov     [rbp+47h+var_59], cl
0x1c010cdd7  movdqu  [rbp+47h+var_78], xmm0
0x1c010cddc  mov     dword ptr [rsp+130h+var_110], edi
0x1c010cde0  call    McTemplateK0qq_UlEtwWriteEventWrapper
0x1c010cde5  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c010cdef  jz      short loc_1C010CE08
0x1c010cdf1  mov     ecx, 1Fh
0x1c010cdf6  lea     rdx, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids
0x1c010cdfd  mov     r9d, r12d
0x1c010ce00  mov     r8d, edi
0x1c010ce03  call    WPP_SF_DD
0x1c010ce08  test    edi, edi
0x1c010ce0a  js      short loc_1C010CE19
0x1c010ce0c  test    r14b, r14b
0x1c010ce0f  jz      short loc_1C010CE19
0x1c010ce11  mov     rcx, rbx
0x1c010ce14  call    UlFlushCacheByServerSession
0x1c010ce19  xor     eax, eax
0x1c010ce1b  mov     [rbp+47h+var_58], rax
0x1c010ce1f  mov     [rbp+47h+var_50], eax
0x1c010ce22  test    rbx, rbx
0x1c010ce25  jz      short loc_1C010CE3C
0x1c010ce27  or      eax, 0FFFFFFFFh
0x1c010ce2a  lock xadd [rbx+4], eax
0x1c010ce2f  cmp     eax, 1
0x1c010ce32  jnz     short loc_1C010CE3C
0x1c010ce34  mov     rcx, rbx; P
0x1c010ce37  call    UlFreeServerSession
0x1c010ce3c  mov     rcx, [r13+38h]
0x1c010ce40  mov     rcx, [rcx+550h]
0x1c010ce47  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c010ce4e  nop     dword ptr [rax+rax+00h]
0x1c010ce53  call    cs:__imp_KeLeaveCriticalRegion
0x1c010ce5a  nop     dword ptr [rax+rax+00h]
0x1c010ce5f  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c010ce69  jz      short loc_1C010CE7F
0x1c010ce6b  mov     ecx, 20h ; ' '
0x1c010ce70  lea     rdx, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids
0x1c010ce77  mov     r8d, edi
0x1c010ce7a  call    WPP_SF_D
0x1c010ce7f  mov     eax, edi
0x1c010ce81  mov     rcx, [rbp+47h+var_48]
0x1c010ce85  xor     rcx, rsp; StackCookie
0x1c010ce88  call    __security_check_cookie
0x1c010ce8d  add     rsp, 0F8h
0x1c010ce94  pop     r15
0x1c010ce96  pop     r14
0x1c010ce98  pop     r13
0x1c010ce9a  pop     r12
0x1c010ce9c  pop     rdi
0x1c010ce9d  pop     rsi
0x1c010ce9e  pop     rbx
0x1c010ce9f  pop     rbp
0x1c010cea0  retn
```
