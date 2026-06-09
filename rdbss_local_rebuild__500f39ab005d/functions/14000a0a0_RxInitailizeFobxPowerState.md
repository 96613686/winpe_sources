# RxInitailizeFobxPowerState

- ea: `0x14000a0a0`
- end: `0x14000a62b`
- name: `RxInitailizeFobxPowerState`
- size: `1419`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x14005d6d0`

## callees

- `0x14000a0a0`
- `0x14000f3f0`
- `0x140014ec0`
- `0x140016e20`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000a13c`
- `ntoskrnl!ExAllocatePool2` at `0x14000a328`
- `ntoskrnl!ExAllocatePool2` at `0x14000a13c`
- `ntoskrnl!ExAllocatePool2` at `0x14000a328`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14000a367`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14000a367`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3eb`
- `ntoskrnl!PsGetProcessId` at `0x14000a350`
- `ntoskrnl!PsGetProcessId` at `0x14000a350`
- `ntoskrnl!PoCreatePowerRequest` at `0x14000a44f`
- `ntoskrnl!PoCreatePowerRequest` at `0x14000a44f`
- `ntoskrnl!KfRaiseIrql` at `0x14000a532`
- `ntoskrnl!KfRaiseIrql` at `0x14000a532`
- `ntoskrnl!KeLowerIrql` at `0x14000a558`
- `ntoskrnl!KeLowerIrql` at `0x14000a558`
- `ntoskrnl!PoSetPowerRequest` at `0x14000a549`
- `ntoskrnl!PoSetPowerRequest` at `0x14000a549`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000a46f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000a46f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a494`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a494`

## string_xrefs

- `0x14000a380`: `wkssvc.dll`

## pseudocode

```c
__int64 __fastcall RxInitailizeFobxPowerState(_QWORD *a1)
{
  __int64 v1; // r13
  PVOID *v2; // rdi
  int v4; // r8d
  __int64 v5; // rdx
  unsigned __int64 v6; // rbx
  _WORD *v7; // r9
  NTSTATUS v8; // r14d
  unsigned __int16 *v9; // r10
  unsigned __int64 v10; // r11
  unsigned __int16 v11; // ax
  _WORD *v12; // r8
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  int v15; // r11d
  __int16 v16; // r10
  unsigned __int16 v17; // r10
  unsigned __int64 v18; // rcx
  unsigned __int16 v19; // ax
  _WORD *v20; // r8
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rbx
  unsigned __int64 v24; // rdx
  _WORD *v25; // r9
  __int16 v26; // r10
  unsigned __int64 v27; // rdx
  struct _KPROCESS *v28; // rcx
  ULONG ProcessId; // eax
  const wchar_t *v30; // rax
  __int64 v31; // rcx
  __int16 v33; // cx
  __int64 v34; // rdx
  __int64 v35; // r8
  char v36; // al
  PVOID v37; // rdi
  KIRQL v38; // bl
  unsigned __int16 v39; // [rsp+30h] [rbp-39h] BYREF
  __int16 v40; // [rsp+32h] [rbp-37h]
  PVOID P; // [rsp+38h] [rbp-31h]
  UNICODE_STRING String; // [rsp+40h] [rbp-29h] BYREF
  _COUNTED_REASON_CONTEXT Context; // [rsp+50h] [rbp-19h] BYREF

  v1 = a1[5];
  v2 = (PVOID *)(a1 + 34);
  Context.ReasonStrings = 0;
  *(_OWORD *)&Context.Version = 0;
  a1[34] = 0;
  *(_OWORD *)&Context.SimpleString.Buffer = 0;
  P = 0;
  String.Buffer = 0;
  v4 = *(_DWORD *)(*(_QWORD *)(v1 + 400) + 336LL);
  if ( (v4 & 0x100) != 0 )
  {
    v5 = *(_QWORD *)(v1 + 120);
    if ( !*(_BYTE *)(v5 + 77) && (*(_DWORD *)(*(_QWORD *)(v5 + 32) + 96LL) & 0x80u) == 0 )
    {
      v6 = (unsigned __int16)(*(_WORD *)(v1 + 360) + **(_WORD **)(v5 + 88));
      P = (PVOID)ExAllocatePool2(258, v6, 1061124178);
      v7 = P;
      if ( !P )
      {
        v8 = -1073741670;
        goto LABEL_48;
      }
      v40 = v6;
      v39 = 0;
      if ( (v6 & 1) != 0 || (_WORD)v6 == 0xFFFF )
      {
        v15 = -1073741811;
LABEL_47:
        v8 = v15;
        goto LABEL_48;
      }
      v8 = -1073741811;
      v9 = *(unsigned __int16 **)(*(_QWORD *)(v1 + 120) + 88LL);
      v10 = *v9;
      if ( (v10 & 1) == 0 )
      {
        v11 = v9[1];
        if ( (v11 & 1) == 0 && v11 != 0xFFFF && (unsigned __int16)v10 <= v11 )
        {
          if ( *((_QWORD *)v9 + 1) || !(_WORD)v10 && !v11 )
          {
            v12 = 0;
            v13 = v6 >> 1;
            v14 = 0;
            if ( v9 )
            {
              v12 = (_WORD *)*((_QWORD *)v9 + 1);
              v14 = v10 >> 1;
            }
            v15 = 0;
            v16 = 0;
            if ( v13 )
            {
              while ( v14 )
              {
                --v14;
                *v7++ = *v12++;
                ++v16;
                if ( !--v13 )
                {
                  LOWORD(v6) = v40;
                  goto LABEL_18;
                }
              }
              LOWORD(v6) = v40;
            }
            else
            {
LABEL_18:
              if ( v14 )
                v15 = -2147483643;
            }
            v2 = (PVOID *)(a1 + 34);
LABEL_21:
            v17 = 2 * v16;
            v39 = v17;
            if ( v15 >= 0 )
            {
              if ( (v6 & 1) == 0 && (_WORD)v6 != 0xFFFF && v17 <= (unsigned __int16)v6 && (P || !v17 && !(_WORD)v6) )
              {
                v18 = *(unsigned __int16 *)(v1 + 360);
                if ( (v18 & 1) == 0 )
                {
                  v19 = *(_WORD *)(v1 + 362);
                  if ( (v19 & 1) == 0
                    && v19 != 0xFFFF
                    && (unsigned __int16)v18 <= v19
                    && (*(_QWORD *)(v1 + 368) || !(_WORD)v18 && !v19) )
                  {
                    v20 = 0;
                    v21 = (unsigned __int16)v6;
                    v22 = 0;
                    v23 = (unsigned __int64)v17 >> 1;
                    v24 = v21 >> 1;
                    if ( v1 != -360 )
                    {
                      v20 = *(_WORD **)(v1 + 368);
                      v22 = v18 >> 1;
                    }
                    v25 = (char *)P + 2 * v23;
                    v8 = 0;
                    v26 = 0;
                    v27 = v24 - v23;
                    if ( v27 )
                    {
                      while ( v22 )
                      {
                        --v22;
                        *v25++ = *v20++;
                        ++v26;
                        if ( !--v27 )
                          goto LABEL_36;
                      }
                    }
                    else
                    {
LABEL_36:
                      if ( v22 )
                        v8 = -2147483643;
                    }
                    v39 = 2 * (v23 + v26);
                    if ( v8 >= 0 )
                    {
                      String.Buffer = (wchar_t *)ExAllocatePool2(258, 22, 1061124178);
                      if ( String.Buffer )
                      {
                        v28 = (struct _KPROCESS *)a1[32];
                        *(_DWORD *)&String.Length = 1441792;
                        ProcessId = (unsigned int)PsGetProcessId(v28);
                        v8 = RtlIntegerToUnicodeString(ProcessId, 0xAu, &String);
                        if ( v8 >= 0 )
                        {
                          Context.Version = 0;
                          Context.Flags = 2;
                          Context.ResourceFileName = 0;
                          v30 = L"wkssvc.dll";
                          v31 = 0x7FFF;
                          while ( *v30 )
                          {
                            ++v30;
                            if ( !--v31 )
                              goto LABEL_54;
                          }
                          v33 = 2 * v31;
                          Context.ResourceFileName.Buffer = L"wkssvc.dll";
                          Context.ResourceFileName.Length = -2 - v33;
                          Context.ResourceFileName.MaximumLength = -v33;
LABEL_54:
                          Context.StringCount = 2;
                          Context.ResourceReasonId = 105;
                          Context.ReasonStrings = (PUNICODE_STRING)&v39;
                          v8 = PoCreatePowerRequest(v2, &RxFileSystemDeviceObject->DeviceObject, &Context);
                          if ( v8 < 0 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) )
                            {
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                11,
                                WPP_f7b911ab27703f80413b896855cb6f75_Traceguids,
                                (unsigned int)v8);
                            }
                          }
                          else
                          {
                            ExAcquirePushLockExclusiveEx(&RxPowerContext, 0);
                            v36 = *(_BYTE *)(v1 + 282);
                            if ( v36 && (v36 & 1) == 0 )
                            {
                              if ( (v36 & 2) != 0 )
                              {
                                if ( byte_140038BD8 == 1 )
                                {
                                  v37 = *v2;
                                  v38 = KfRaiseIrql(2u);
                                  PoSetPowerRequest(v37, PowerRequestSystemRequired);
                                  KeLowerIrql(v38);
                                }
                              }
                              else if ( (v36 & 4) != 0 )
                              {
                                LOBYTE(v35) = 4;
                                LOBYTE(v34) = 1;
                                RxUpdateFobxPowerState(a1, v34, v35);
                              }
                            }
                            ExReleasePushLockExclusiveEx(&RxPowerContext, 0);
                          }
                        }
                      }
                      else
                      {
                        v8 = -1073741670;
                      }
                    }
                  }
                }
              }
              goto LABEL_48;
            }
            goto LABEL_47;
          }
          v2 = (PVOID *)(a1 + 34);
        }
      }
      v16 = 0;
      v15 = -1073741811;
      goto LABEL_21;
    }
  }
  v8 = 0;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    return (unsigned int)v8;
  }
  WPP_SF_qDD(
    WPP_GLOBAL_Control->AttachedDevice,
    10,
    WPP_f7b911ab27703f80413b896855cb6f75_Traceguids,
    a1,
    v4,
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 120) + 32LL) + 96LL));
LABEL_48:
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    P = 0;
  }
  if ( String.Buffer )
    ExFreePoolWithTag(String.Buffer, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000a0a0  push    rbp
0x14000a0a2  push    rbx
0x14000a0a3  push    rsi
0x14000a0a4  push    rdi
0x14000a0a5  push    r12
0x14000a0a7  push    r13
0x14000a0a9  push    r14
0x14000a0ab  push    r15
0x14000a0ad  lea     rbp, [rsp-1Fh]
0x14000a0b2  sub     rsp, 88h
0x14000a0b9  mov     r13, [rcx+28h]
0x14000a0bd  lea     rdi, [rcx+110h]
0x14000a0c4  xor     esi, esi
0x14000a0c6  xor     eax, eax
0x14000a0c8  xorps   xmm0, xmm0
0x14000a0cb  mov     qword ptr [rbp+57h+Context.8+18h], rax
0x14000a0cf  movups  xmmword ptr [rbp+57h+Context.Version], xmm0
0x14000a0d3  mov     [rdi], rsi
0x14000a0d6  mov     r12, rcx
0x14000a0d9  movups  xmmword ptr [rbp+57h+Context.8+8], xmm0
0x14000a0dd  mov     [rbp+57h+P], rsi
0x14000a0e1  mov     [rbp+57h+String.Buffer], rsi
0x14000a0e5  mov     rax, [r13+190h]
0x14000a0ec  mov     r8d, [rax+150h]
0x14000a0f3  bt      r8d, 8
0x14000a0f8  jnb     loc_14000A4B0
0x14000a0fe  mov     rdx, [r13+78h]
0x14000a102  cmp     [rdx+4Dh], sil
0x14000a106  jnz     loc_14000A4B0
0x14000a10c  mov     rax, [rdx+20h]
0x14000a110  mov     ecx, [rax+60h]
0x14000a113  test    cl, cl
0x14000a115  js      loc_14000A4B0
0x14000a11b  mov     rax, [rdx+58h]
0x14000a11f  lea     rsi, [r13+168h]
0x14000a126  mov     r8d, 3F3F7852h
0x14000a12c  mov     ecx, 102h
0x14000a131  movzx   edx, word ptr [rax]
0x14000a134  add     dx, [rsi]
0x14000a137  movzx   ebx, dx
0x14000a13a  mov     edx, ebx
0x14000a13c  call    cs:__imp_ExAllocatePool2
0x14000a143  nop     dword ptr [rax+rax+00h]
0x14000a148  mov     [rbp+57h+P], rax
0x14000a14c  mov     r9, rax
0x14000a14f  test    rax, rax
0x14000a152  jz      loc_14000A569
0x14000a158  xor     eax, eax
0x14000a15a  mov     [rbp+57h+var_8E], bx
0x14000a15e  mov     [rbp+57h+var_90], ax
0x14000a162  test    bl, 1
0x14000a165  jnz     loc_14000A3BA
0x14000a16b  mov     r15d, 0FFFEh
0x14000a171  cmp     bx, r15w
0x14000a175  ja      loc_14000A3BA
0x14000a17b  mov     rax, [r13+78h]
0x14000a17f  mov     r14d, 0C000000Dh
0x14000a185  mov     r10, [rax+58h]
0x14000a189  movzx   r11d, word ptr [r10]
0x14000a18d  test    r11b, 1
0x14000a191  jnz     loc_14000A4A5
0x14000a197  movzx   eax, word ptr [r10+2]
0x14000a19c  test    al, 1
0x14000a19e  jnz     loc_14000A4A5
0x14000a1a4  cmp     ax, r15w
0x14000a1a8  ja      loc_14000A4A5
0x14000a1ae  cmp     r11w, ax
0x14000a1b2  ja      loc_14000A4A5
0x14000a1b8  mov     rdi, [r10+8]
0x14000a1bc  test    rdi, rdi
0x14000a1bf  jz      loc_14000A576
0x14000a1c5  mov     rdx, rbx
0x14000a1c8  xor     r8d, r8d
0x14000a1cb  shr     rdx, 1
0x14000a1ce  xor     ecx, ecx
0x14000a1d0  test    r10, r10
0x14000a1d3  jz      short loc_14000A1DE
0x14000a1d5  mov     rcx, r11
0x14000a1d8  mov     r8, rdi
0x14000a1db  shr     rcx, 1
0x14000a1de  xor     r11d, r11d
0x14000a1e1  xor     r10d, r10d
0x14000a1e4  test    rdx, rdx
0x14000a1e7  jz      short loc_14000A219
0x14000a1e9  nop     dword ptr [rax+00000000h]
0x14000a1f0  test    rcx, rcx
0x14000a1f3  jz      loc_14000A3B1
0x14000a1f9  movzx   eax, word ptr [r8]
0x14000a1fd  dec     rcx
0x14000a200  mov     [r9], ax
0x14000a204  add     r8, 2
0x14000a208  add     r9, 2
0x14000a20c  inc     r10
0x14000a20f  sub     rdx, 1
0x14000a213  jnz     short loc_14000A1F0
0x14000a215  movzx   ebx, [rbp+57h+var_8E]
0x14000a219  test    rcx, rcx
0x14000a21c  jz      short loc_14000A224
0x14000a21e  mov     r11d, 80000005h
0x14000a224  lea     rdi, [r12+110h]
0x14000a22c  add     r10w, r10w
0x14000a230  mov     [rbp+57h+var_90], r10w
0x14000a235  test    r11d, r11d
0x14000a238  js      loc_14000A3C0
0x14000a23e  test    bl, 1
0x14000a241  jnz     loc_14000A3C3
0x14000a247  cmp     bx, r15w
0x14000a24b  ja      loc_14000A3C3
0x14000a251  cmp     r10w, bx
0x14000a255  ja      loc_14000A3C3
0x14000a25b  cmp     [rbp+57h+P], 0
0x14000a260  jz      loc_14000A58E
0x14000a266  movzx   ecx, word ptr [rsi]
0x14000a269  test    cl, 1
0x14000a26c  jnz     loc_14000A3C3
0x14000a272  movzx   eax, word ptr [rsi+2]
0x14000a276  test    al, 1
0x14000a278  jnz     loc_14000A3C3
0x14000a27e  cmp     ax, r15w
0x14000a282  ja      loc_14000A3C3
0x14000a288  cmp     cx, ax
0x14000a28b  ja      loc_14000A3C3
0x14000a291  mov     r9, [rsi+8]
0x14000a295  test    r9, r9
0x14000a298  jz      loc_14000A5A6
0x14000a29e  mov     r11, [rbp+57h+P]
0x14000a2a2  xor     r8d, r8d
0x14000a2a5  movzx   edx, bx
0x14000a2a8  xor     eax, eax
0x14000a2aa  movzx   ebx, r10w
0x14000a2ae  shr     rbx, 1
0x14000a2b1  shr     rdx, 1
0x14000a2b4  test    rsi, rsi
0x14000a2b7  jz      short loc_14000A2C2
0x14000a2b9  mov     rax, rcx
0x14000a2bc  mov     r8, r9
0x14000a2bf  shr     rax, 1
0x14000a2c2  lea     r9, [r11+rbx*2]
0x14000a2c6  mov     esi, 0
0x14000a2cb  mov     r14d, esi
0x14000a2ce  mov     r10d, esi
0x14000a2d1  sub     rdx, rbx
0x14000a2d4  jz      short loc_14000A2F7
0x14000a2d6  test    rax, rax
0x14000a2d9  jz      short loc_14000A302
0x14000a2db  movzx   ecx, word ptr [r8]
0x14000a2df  dec     rax
0x14000a2e2  mov     [r9], cx
0x14000a2e6  add     r8, 2
0x14000a2ea  add     r9, 2
0x14000a2ee  inc     r10
0x14000a2f1  sub     rdx, 1
0x14000a2f5  jnz     short loc_14000A2D6
0x14000a2f7  test    rax, rax
0x14000a2fa  jz      short loc_14000A302
0x14000a2fc  mov     r14d, 80000005h
0x14000a302  add     r10w, bx
0x14000a306  add     r10w, r10w
0x14000a30a  mov     [rbp+57h+var_90], r10w
0x14000a30f  test    r14d, r14d
0x14000a312  js      loc_14000A3C5
0x14000a318  mov     edx, 16h
0x14000a31d  mov     ecx, 102h
0x14000a322  mov     r8d, 3F3F7852h
0x14000a328  call    cs:__imp_ExAllocatePool2
0x14000a32f  nop     dword ptr [rax+rax+00h]
0x14000a334  mov     [rbp+57h+String.Buffer], rax
0x14000a338  test    rax, rax
0x14000a33b  jz      loc_14000A5BD
0x14000a341  mov     rcx, [r12+100h]; Process
0x14000a349  mov     dword ptr [rbp+57h+String.Length], 160000h
0x14000a350  call    cs:__imp_PsGetProcessId
0x14000a357  nop     dword ptr [rax+rax+00h]
0x14000a35c  lea     r8, [rbp+57h+String]; String
0x14000a360  mov     edx, 0Ah; Base
0x14000a365  mov     ecx, eax; Value
0x14000a367  call    cs:__imp_RtlIntegerToUnicodeString
0x14000a36e  nop     dword ptr [rax+rax+00h]
0x14000a373  mov     r14d, eax
0x14000a376  test    eax, eax
0x14000a378  js      short loc_14000A3C5
0x14000a37a  xorps   xmm0, xmm0
0x14000a37d  mov     [rbp+57h+Context.Version], esi
0x14000a380  lea     rdx, aWkssvcDll; "wkssvc.dll"
0x14000a387  mov     [rbp+57h+Context.Flags], 2
0x14000a38e  movups  xmmword ptr [rbp+57h+Context.8], xmm0
0x14000a392  mov     rax, rdx
0x14000a395  mov     ecx, 7FFFh
0x14000a39a  nop     word ptr [rax+rax+00h]
0x14000a3a0  cmp     [rax], si
0x14000a3a3  jz      short loc_14000A40F
0x14000a3a5  add     rax, 2
0x14000a3a9  sub     rcx, 1
0x14000a3ad  jnz     short loc_14000A3A0
0x14000a3af  jmp     short loc_14000A429
0x14000a3b1  movzx   ebx, [rbp+57h+var_8E]
0x14000a3b5  jmp     loc_14000A224
0x14000a3ba  mov     r11d, 0C000000Dh
0x14000a3c0  mov     r14d, r11d
0x14000a3c3  xor     esi, esi
0x14000a3c5  mov     rcx, [rbp+57h+P]; P
0x14000a3c9  test    rcx, rcx
0x14000a3cc  jz      short loc_14000A3E0
0x14000a3ce  xor     edx, edx; Tag
0x14000a3d0  call    cs:__imp_ExFreePoolWithTag
0x14000a3d7  nop     dword ptr [rax+rax+00h]
0x14000a3dc  mov     [rbp+57h+P], rsi
0x14000a3e0  mov     rcx, [rbp+57h+String.Buffer]; P
0x14000a3e4  test    rcx, rcx
0x14000a3e7  jz      short loc_14000A3F7
0x14000a3e9  xor     edx, edx; Tag
0x14000a3eb  call    cs:__imp_ExFreePoolWithTag
0x14000a3f2  nop     dword ptr [rax+rax+00h]
0x14000a3f7  mov     eax, r14d
0x14000a3fa  add     rsp, 88h
0x14000a401  pop     r15
0x14000a403  pop     r14
0x14000a405  pop     r13
0x14000a407  pop     r12
0x14000a409  pop     rdi
0x14000a40a  pop     rsi
0x14000a40b  pop     rbx
0x14000a40c  pop     rbp
0x14000a40d  retn
0x14000a40f  add     cx, cx
0x14000a412  mov     qword ptr [rbp+57h+Context.8+8], rdx
0x14000a416  sub     r15w, cx
0x14000a41a  mov     word ptr [rbp+57h+Context.8], r15w
0x14000a41f  add     r15w, 2
0x14000a424  mov     word ptr [rbp+57h+Context.8+2], r15w
0x14000a429  mov     rdx, cs:RxFileSystemDeviceObject; DeviceObject
0x14000a430  lea     r8, [rbp+57h+Context]; Context
0x14000a434  mov     eax, 69h ; 'i'
0x14000a439  mov     dword ptr [rbp+57h+Context.8+14h], 2
0x14000a440  mov     word ptr [rbp+57h+Context.8+10h], ax
0x14000a444  mov     rcx, rdi; PowerRequest
0x14000a447  lea     rax, [rbp+57h+var_90]
0x14000a44b  mov     qword ptr [rbp+57h+Context.8+18h], rax
0x14000a44f  call    cs:__imp_PoCreatePowerRequest
0x14000a456  nop     dword ptr [rax+rax+00h]
0x14000a45b  mov     r14d, eax
0x14000a45e  test    eax, eax
0x14000a460  js      loc_14000A5C8
0x14000a466  xor     edx, edx
0x14000a468  lea     rcx, RxPowerContext
0x14000a46f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000a476  nop     dword ptr [rax+rax+00h]
0x14000a47b  movzx   eax, byte ptr [r13+11Ah]
0x14000a483  test    al, al
0x14000a485  jnz     loc_14000A510
0x14000a48b  xor     edx, edx
0x14000a48d  lea     rcx, RxPowerContext
0x14000a494  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000a49b  nop     dword ptr [rax+rax+00h]
0x14000a4a0  jmp     loc_14000A3C5
0x14000a4a5  xor     r10d, r10d
0x14000a4a8  mov     r11d, r14d
0x14000a4ab  jmp     loc_14000A22C
0x14000a4b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4b7  lea     rax, WPP_GLOBAL_Control
0x14000a4be  mov     r14d, esi
0x14000a4c1  cmp     rcx, rax
0x14000a4c4  jz      loc_14000A3F7
0x14000a4ca  mov     eax, [rcx+2Ch]
0x14000a4cd  test    al, 2
0x14000a4cf  jz      loc_14000A3F7
0x14000a4d5  cmp     byte ptr [rcx+29h], 2
0x14000a4d9  jb      loc_14000A3F7
0x14000a4df  mov     rax, [r13+78h]
0x14000a4e3  mov     edx, 0Ah
0x14000a4e8  mov     rcx, [rcx+18h]
0x14000a4ec  mov     r9, r12
0x14000a4ef  mov     rax, [rax+20h]
0x14000a4f3  mov     eax, [rax+60h]
0x14000a4f6  mov     [rsp+0C0h+var_98], eax
0x14000a4fa  mov     [rsp+0C0h+var_A0], r8d
0x14000a4ff  lea     r8, WPP_f7b911ab27703f80413b896855cb6f75_Traceguids
0x14000a506  call    WPP_SF_qDD
0x14000a50b  jmp     loc_14000A3C5
0x14000a510  test    al, 1
0x14000a512  jnz     loc_14000A48B
0x14000a518  test    al, 2
0x14000a51a  jz      loc_14000A611
0x14000a520  cmp     cs:byte_140038BD8, 1
0x14000a527  jnz     loc_14000A48B
0x14000a52d  mov     rdi, [rdi]
0x14000a530  mov     cl, 2; NewIrql
0x14000a532  call    cs:__imp_KfRaiseIrql
0x14000a539  nop     dword ptr [rax+rax+00h]
0x14000a53e  mov     edx, 1; Type
0x14000a543  mov     rcx, rdi; PowerRequest
0x14000a546  movzx   ebx, al
0x14000a549  call    cs:__imp_PoSetPowerRequest
0x14000a550  nop     dword ptr [rax+rax+00h]
0x14000a555  movzx   ecx, bl; NewIrql
0x14000a558  call    cs:__imp_KeLowerIrql
0x14000a55f  nop     dword ptr [rax+rax+00h]
0x14000a564  jmp     loc_14000A48B
0x14000a569  xor     esi, esi
0x14000a56b  mov     r14d, 0C000009Ah
  ... truncated ...
```
