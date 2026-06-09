# CldiStreamServiceHydrationRequest

- ea: `0x14007886c`
- end: `0x140078d3a`
- name: `CldiStreamServiceHydrationRequest`
- size: `1230`
- prototype: `__int64 __fastcall(__int64 **, __int64, __int64, char *, __int64, _BYTE *, _BYTE *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x14006d198`
- `0x140082ba0`

## callees

- `0x140003c50`
- `0x140010e68`
- `0x140010f14`
- `0x140011044`
- `0x1400110f0`
- `0x1400111ac`
- `0x14001e300`
- `0x14007886c`

## import_xrefs

- `ntoskrnl!FsRtlLookupBaseMcbEntry` at `0x140078a27`
- `ntoskrnl!FsRtlLookupBaseMcbEntry` at `0x140078a27`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x1400789e3`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x1400789e3`

## pseudocode

```c
__int64 __fastcall CldiStreamServiceHydrationRequest(
        __int64 **a1,
        __int64 a2,
        __int64 a3,
        char *a4,
        __int64 a5,
        _BYTE *a6,
        _BYTE *a7)
{
  __int64 v9; // r13
  __int64 v10; // r9
  int v11; // r15d
  __int64 v12; // r10
  __int64 v14; // rbp
  __int64 v15; // rcx
  __int64 v16; // r14
  signed __int64 v17; // r15
  __int64 v18; // rsi
  __int64 v19; // r14
  __int64 v20; // r13
  __int64 v21; // rbp
  __int64 v22; // rdi
  __int64 v23; // r14
  unsigned int v24; // esi
  __int64 v25; // r8
  __int64 *v27; // rax
  __int64 v28; // rdx
  char *v29; // rsi
  __int64 v30; // rcx
  __int64 v31; // r14
  signed __int64 v32; // r14
  __int64 *v33; // rax
  __int64 v34; // rdx
  __int64 *v35; // rax
  __int64 v36; // rdx
  __int64 *v37; // rax
  __int64 v38; // r8
  __int64 *v39; // rax
  __int64 v40; // rdx
  __int64 Lbn; // [rsp+60h] [rbp-48h] BYREF
  __int64 SectorCountFromLbn[8]; // [rsp+68h] [rbp-40h] BYREF
  __int64 v44; // [rsp+B8h] [rbp+10h]
  __int64 v46; // [rsp+D0h] [rbp+28h]

  v9 = 0x7FFFFFFFFFFFFFFFLL;
  v10 = **a1;
  v11 = *(_DWORD *)(v10 + 28);
  v12 = *(_QWORD *)(*(_QWORD *)(v10 + 16) + 32LL);
  v44 = v12;
  Lbn = 0;
  SectorCountFromLbn[0] = 0;
  if ( a3 != -1 )
    v9 = a2 + a3;
  v14 = *(_QWORD *)(a5 + 352);
  v15 = *(_QWORD *)(a5 + 360);
  if ( a7 )
    *a7 = 0;
  if ( v9 <= v14 || (v16 = v15 + v14, v46 = v15 + v14, v15 + v14 <= a2) )
  {
    v24 = 0;
    *a6 = 0;
  }
  else
  {
    v17 = (unsigned __int64)(~(_BYTE)v11 & 2) << 11;
    if ( a7 )
      *a7 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v27 = *(__int64 **)(a5 + 96);
      if ( v27 )
        v28 = *v27;
      else
        v28 = 0;
      WPP_SF_iqqiiiiq(
        WPP_GLOBAL_Control->AttachedDevice,
        v28,
        a3,
        v12,
        a5,
        v28,
        *(_QWORD *)(a5 + 352),
        *(_QWORD *)(a5 + 360),
        a2,
        a3,
        a4);
      v12 = v44;
    }
    if ( a4 )
    {
      v29 = *(char **)(a5 + 328);
      if ( v29 )
      {
        v30 = *(_QWORD *)(a5 + 336);
        v31 = v30 + *(int *)(a5 + 344);
        if ( v30 > a2 )
          a4 += v30 - a2;
        else
          v29 = &v29[a2 - v30];
        if ( v9 < v31 )
          v31 = v9;
        if ( a2 > v30 )
          v30 = a2;
        v32 = v31 - v30;
        if ( v32 > 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            v33 = *(__int64 **)(a5 + 96);
            if ( v33 )
              v34 = *v33;
            else
              v34 = 0;
            WPP_SF_iqqqqi(WPP_GLOBAL_Control->AttachedDevice, v34, a3, v12, a5, v34, v29, a4, v32);
          }
          memmove(v29, a4, v32);
        }
        v16 = v46;
      }
    }
    if ( v14 > a2 )
      v18 = 0;
    else
      v18 = a2 - v14;
    if ( v9 < v16 )
      v16 = v9;
    if ( a2 > v14 )
      v14 = a2;
    v19 = v16 - v14;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v35 = *(__int64 **)(a5 + 96);
      if ( v35 )
        v36 = *v35;
      else
        v36 = 0;
      v20 = v44;
      WPP_SF_iqqqiiii(
        WPP_GLOBAL_Control->AttachedDevice,
        v36,
        a3,
        v44,
        *a1,
        a5,
        v36,
        *(_QWORD *)(a5 + 352),
        *(_QWORD *)(a5 + 360),
        v18,
        v19);
    }
    else
    {
      v20 = v44;
    }
    v21 = ~(v17 - 1);
    if ( FsRtlAddBaseMcbEntry(
           (PBASE_MCB)(a5 + 304),
           (v18 & v21) / v17,
           (v18 & v21) / v17 + 1,
           ((v21 & (v18 + v19 + v17 - 1)) - (v18 & v21)) / v17) )
    {
      v22 = *(_QWORD *)(a5 + 352);
      v23 = *(_QWORD *)(a5 + 360);
      v24 = 0;
      if ( FsRtlLookupBaseMcbEntry((PBASE_MCB)(a5 + 304), 0, &Lbn, SectorCountFromLbn, 0, 0, 0)
        && Lbn != -1
        && SectorCountFromLbn[0] >= ((v21 & (v17 + v23 + v22 - 1)) - (v22 & v21)) / v17 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v39 = *(__int64 **)(a5 + 96);
          if ( v39 )
            v40 = *v39;
          else
            v40 = 0;
          WPP_SF_iqqqii(
            WPP_GLOBAL_Control->AttachedDevice,
            v40,
            v25,
            v20,
            *a1,
            a5,
            v40,
            *(_QWORD *)(a5 + 352),
            *(_QWORD *)(a5 + 360));
        }
        *a6 = 1;
      }
    }
    else
    {
      v24 = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v37 = *(__int64 **)(a5 + 96);
        if ( v37 )
          v38 = *v37;
        else
          v38 = 0;
        WPP_SF_iqqqiiiid(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          v38,
          v20,
          *a1,
          a5,
          v38,
          *(_QWORD *)(a5 + 352),
          *(_QWORD *)(a5 + 360),
          a2,
          a3,
          -1073741670);
      }
    }
  }
  return v24;
}

```

## disassembly

```asm
0x14007886c  mov     r11, rsp
0x14007886f  mov     [r11+20h], rbx
0x140078873  mov     [r11+18h], r8
0x140078877  mov     [r11+8], rcx
0x14007887b  push    rbp
0x14007887c  push    rsi
0x14007887d  push    rdi
0x14007887e  push    r12
0x140078880  push    r13
0x140078882  push    r14
0x140078884  push    r15
0x140078886  sub     rsp, 70h
0x14007888a  mov     rax, [rcx]
0x14007888d  mov     r12, r9
0x140078890  mov     rdi, rdx
0x140078893  mov     r13, 7FFFFFFFFFFFFFFFh
0x14007889d  mov     r9, [rax]
0x1400788a0  mov     rax, [r9+10h]
0x1400788a4  mov     r15d, [r9+1Ch]
0x1400788a8  mov     r10, [rax+20h]
0x1400788ac  mov     [rsp+0A8h+arg_8], r10
0x1400788b4  mov     qword ptr [r11-48h], 0
0x1400788bc  mov     qword ptr [r11-40h], 0
0x1400788c4  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1400788c8  jz      short loc_1400788CE
0x1400788ca  lea     r13, [rdx+r8]
0x1400788ce  mov     rbx, [rsp+0A8h+arg_20]
0x1400788d6  mov     rax, [rsp+0A8h+arg_30]
0x1400788de  mov     rbp, [rbx+160h]
0x1400788e5  mov     rcx, [rbx+168h]
0x1400788ec  test    rax, rax
0x1400788ef  jz      short loc_1400788F4
0x1400788f1  mov     byte ptr [rax], 0
0x1400788f4  cmp     r13, rbp
0x1400788f7  jle     loc_140078A7D
0x1400788fd  lea     r14, [rcx+rbp]
0x140078901  mov     [rsp+0A8h+arg_20], r14
0x140078909  cmp     r14, rdi
0x14007890c  jle     loc_140078A7D
0x140078912  not     r15d
0x140078915  and     r15d, 2
0x140078919  shl     r15, 0Bh
0x14007891d  test    rax, rax
0x140078920  jz      short loc_140078925
0x140078922  mov     byte ptr [rax], 1
0x140078925  mov     rcx, cs:WPP_GLOBAL_Control
0x14007892c  lea     rdx, WPP_GLOBAL_Control
0x140078933  cmp     rcx, rdx
0x140078936  jz      short loc_14007894B
0x140078938  test    dword ptr [rcx+2Ch], 100h
0x14007893f  jz      short loc_14007894B
0x140078941  cmp     byte ptr [rcx+29h], 4
0x140078945  jnb     loc_140078A93
0x14007894b  test    r12, r12
0x14007894e  jnz     loc_140078AF4
0x140078954  cmp     rbp, rdi
0x140078957  jg      loc_140078A8C
0x14007895d  mov     rsi, rdi
0x140078960  sub     rsi, rbp
0x140078963  cmp     r13, r14
0x140078966  cmovl   r14, r13
0x14007896a  cmp     rdi, rbp
0x14007896d  cmovg   rbp, rdi
0x140078971  sub     r14, rbp
0x140078974  mov     rcx, cs:WPP_GLOBAL_Control
0x14007897b  lea     rax, WPP_GLOBAL_Control
0x140078982  cmp     rcx, rax
0x140078985  jz      short loc_14007899A
0x140078987  test    dword ptr [rcx+2Ch], 100h
0x14007898e  jz      short loc_14007899A
0x140078990  cmp     byte ptr [rcx+29h], 4
0x140078994  jnb     loc_140078BAC
0x14007899a  mov     r13, [rsp+0A8h+arg_8]
0x1400789a2  lea     rbp, [r15-1]
0x1400789a6  not     rbp
0x1400789a9  lea     r12, [rbx+130h]
0x1400789b0  mov     r8, rbp
0x1400789b3  mov     rcx, r12; Mcb
0x1400789b6  and     r8, rsi
0x1400789b9  mov     rax, r8
0x1400789bc  cqo
0x1400789be  idiv    r15
0x1400789c1  mov     r10, rax
0x1400789c4  lea     rax, [r15-1]
0x1400789c8  add     rax, r14
0x1400789cb  add     rax, rsi
0x1400789ce  and     rax, rbp
0x1400789d1  sub     rax, r8
0x1400789d4  lea     r8, [r10+1]; Lbn
0x1400789d8  cqo
0x1400789da  idiv    r15
0x1400789dd  mov     rdx, r10; Vbn
0x1400789e0  mov     r9, rax; SectorCount
0x1400789e3  call    cs:__imp_FsRtlAddBaseMcbEntry
0x1400789ea  nop     dword ptr [rax+rax+00h]
0x1400789ef  xor     ecx, ecx
0x1400789f1  test    al, al
0x1400789f3  jz      loc_140078C11
0x1400789f9  mov     rdi, [rbx+160h]
0x140078a00  lea     r9, [rsp+0A8h+SectorCountFromLbn]; SectorCountFromLbn
0x140078a05  mov     r14, [rbx+168h]
0x140078a0c  lea     r8, [rsp+0A8h+Lbn]; Lbn
0x140078a11  mov     [rsp+0A8h+Index], rcx; Index
0x140078a16  mov     esi, ecx
0x140078a18  mov     [rsp+0A8h+SectorCountFromStartingLbn], rcx; SectorCountFromStartingLbn
0x140078a1d  xor     edx, edx; Vbn
0x140078a1f  mov     [rsp+0A8h+StartingLbn], rcx; StartingLbn
0x140078a24  mov     rcx, r12; Mcb
0x140078a27  call    cs:__imp_FsRtlLookupBaseMcbEntry
0x140078a2e  nop     dword ptr [rax+rax+00h]
0x140078a33  test    al, al
0x140078a35  jz      short loc_140078A62
0x140078a37  cmp     [rsp+0A8h+Lbn], 0FFFFFFFFFFFFFFFFh
0x140078a3d  jz      short loc_140078A62
0x140078a3f  lea     rax, [rdi-1]
0x140078a43  add     rax, r14
0x140078a46  add     rax, r15
0x140078a49  and     rax, rbp
0x140078a4c  and     rbp, rdi
0x140078a4f  sub     rax, rbp
0x140078a52  cqo
0x140078a54  idiv    r15
0x140078a57  cmp     [rsp+0A8h+SectorCountFromLbn], rax
0x140078a5c  jge     loc_140078CBA
0x140078a62  mov     rbx, [rsp+0A8h+arg_18]
0x140078a6a  mov     eax, esi
0x140078a6c  add     rsp, 70h
0x140078a70  pop     r15
0x140078a72  pop     r14
0x140078a74  pop     r13
0x140078a76  pop     r12
0x140078a78  pop     rdi
0x140078a79  pop     rsi
0x140078a7a  pop     rbp
0x140078a7b  retn
0x140078a7d  mov     rcx, [rsp+0A8h+arg_28]
0x140078a85  xor     esi, esi
0x140078a87  mov     [rcx], sil
0x140078a8a  jmp     short loc_140078A62
0x140078a8c  xor     esi, esi
0x140078a8e  jmp     loc_140078963
0x140078a93  mov     rax, [rbx+60h]
0x140078a97  test    rax, rax
0x140078a9a  jz      short loc_140078AA1
0x140078a9c  mov     rdx, [rax]
0x140078a9f  jmp     short loc_140078AA3
0x140078aa1  xor     edx, edx
0x140078aa3  mov     rax, [rbx+168h]
0x140078aaa  mov     r9, r10
0x140078aad  mov     rcx, [rcx+18h]
0x140078ab1  mov     [rsp+0A8h+var_58], r12
0x140078ab6  mov     [rsp+0A8h+var_60], r8
0x140078abb  mov     [rsp+0A8h+var_68], rdi
0x140078ac0  mov     [rsp+0A8h+var_70], rax
0x140078ac5  mov     rax, [rbx+160h]
0x140078acc  mov     [rsp+0A8h+Index], rax
0x140078ad1  mov     [rsp+0A8h+SectorCountFromStartingLbn], rdx
0x140078ad6  mov     [rsp+0A8h+StartingLbn], rbx
0x140078adb  call    WPP_SF_iqqiiiiq
0x140078ae0  mov     r10, [rsp+0A8h+arg_8]
0x140078ae8  lea     rdx, WPP_GLOBAL_Control
0x140078aef  jmp     loc_14007894B
0x140078af4  mov     rsi, [rbx+148h]
0x140078afb  test    rsi, rsi
0x140078afe  jz      loc_140078954
0x140078b04  mov     rcx, [rbx+150h]
0x140078b0b  movsxd  r14, dword ptr [rbx+158h]
0x140078b12  add     r14, rcx
0x140078b15  cmp     rcx, rdi
0x140078b18  jg      short loc_140078B22
0x140078b1a  sub     rsi, rcx
0x140078b1d  add     rsi, rdi
0x140078b20  jmp     short loc_140078B2B
0x140078b22  mov     rax, rcx
0x140078b25  sub     rax, rdi
0x140078b28  add     r12, rax
0x140078b2b  cmp     r13, r14
0x140078b2e  cmovl   r14, r13
0x140078b32  cmp     rdi, rcx
0x140078b35  cmovg   rcx, rdi
0x140078b39  sub     r14, rcx
0x140078b3c  test    r14, r14
0x140078b3f  jle     short loc_140078B9F
0x140078b41  mov     rcx, cs:WPP_GLOBAL_Control
0x140078b48  cmp     rcx, rdx
0x140078b4b  jz      short loc_140078B91
0x140078b4d  test    dword ptr [rcx+2Ch], 100h
0x140078b54  jz      short loc_140078B91
0x140078b56  cmp     byte ptr [rcx+29h], 4
0x140078b5a  jb      short loc_140078B91
0x140078b5c  mov     rax, [rbx+60h]
0x140078b60  test    rax, rax
0x140078b63  jz      short loc_140078B6A
0x140078b65  mov     rdx, [rax]
0x140078b68  jmp     short loc_140078B6C
0x140078b6a  xor     edx, edx
0x140078b6c  mov     rcx, [rcx+18h]
0x140078b70  mov     r9, r10
0x140078b73  mov     [rsp+0A8h+var_68], r14
0x140078b78  mov     [rsp+0A8h+var_70], r12
0x140078b7d  mov     [rsp+0A8h+Index], rsi
0x140078b82  mov     [rsp+0A8h+SectorCountFromStartingLbn], rdx
0x140078b87  mov     [rsp+0A8h+StartingLbn], rbx
0x140078b8c  call    WPP_SF_iqqqqi
0x140078b91  mov     r8, r14; Size
0x140078b94  mov     rdx, r12; Src
0x140078b97  mov     rcx, rsi; void *
0x140078b9a  call    memmove
0x140078b9f  mov     r14, [rsp+0A8h+arg_20]
0x140078ba7  jmp     loc_140078954
0x140078bac  mov     rax, [rbx+60h]
0x140078bb0  test    rax, rax
0x140078bb3  jz      short loc_140078BBA
0x140078bb5  mov     rdx, [rax]
0x140078bb8  jmp     short loc_140078BBC
0x140078bba  xor     edx, edx
0x140078bbc  mov     rax, [rbx+168h]
0x140078bc3  mov     r13, [rsp+0A8h+arg_8]
0x140078bcb  mov     rcx, [rcx+18h]
0x140078bcf  mov     r9, r13
0x140078bd2  mov     [rsp+0A8h+var_58], r14
0x140078bd7  mov     [rsp+0A8h+var_60], rsi
0x140078bdc  mov     [rsp+0A8h+var_68], rax
0x140078be1  mov     rax, [rbx+160h]
0x140078be8  mov     [rsp+0A8h+var_70], rax
0x140078bed  mov     rax, [rsp+0A8h+arg_0]
0x140078bf5  mov     [rsp+0A8h+Index], rdx
0x140078bfa  mov     [rsp+0A8h+SectorCountFromStartingLbn], rbx
0x140078bff  mov     rax, [rax]
0x140078c02  mov     [rsp+0A8h+StartingLbn], rax
0x140078c07  call    WPP_SF_iqqqiiii
0x140078c0c  jmp     loc_1400789A2
0x140078c11  mov     esi, 0C000009Ah
0x140078c16  mov     ecx, esi
0x140078c18  call    HsmDbgBreakOnStatus
0x140078c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140078c24  lea     rax, WPP_GLOBAL_Control
0x140078c2b  cmp     rcx, rax
0x140078c2e  jz      loc_140078A62
0x140078c34  test    dword ptr [rcx+2Ch], 100h
0x140078c3b  jz      loc_140078A62
0x140078c41  cmp     byte ptr [rcx+29h], 3
0x140078c45  jb      loc_140078A62
0x140078c4b  mov     rax, [rbx+60h]
0x140078c4f  test    rax, rax
0x140078c52  jz      short loc_140078C59
0x140078c54  mov     r8, [rax]
0x140078c57  jmp     short loc_140078C5C
0x140078c59  xor     r8d, r8d
0x140078c5c  mov     rax, [rsp+0A8h+arg_10]
0x140078c64  mov     edx, 1Ah
0x140078c69  mov     rcx, [rcx+18h]
0x140078c6d  mov     r9, r13
0x140078c70  mov     [rsp+0A8h+var_50], esi
0x140078c74  mov     [rsp+0A8h+var_58], rax
0x140078c79  mov     rax, [rbx+168h]
0x140078c80  mov     [rsp+0A8h+var_60], rdi
0x140078c85  mov     [rsp+0A8h+var_68], rax
0x140078c8a  mov     rax, [rbx+160h]
0x140078c91  mov     [rsp+0A8h+var_70], rax
0x140078c96  mov     rax, [rsp+0A8h+arg_0]
0x140078c9e  mov     [rsp+0A8h+Index], r8
0x140078ca3  mov     [rsp+0A8h+SectorCountFromStartingLbn], rbx
0x140078ca8  mov     rax, [rax]
0x140078cab  mov     [rsp+0A8h+StartingLbn], rax
0x140078cb0  call    WPP_SF_iqqqiiiid
0x140078cb5  jmp     loc_140078A62
0x140078cba  mov     rcx, cs:WPP_GLOBAL_Control
0x140078cc1  lea     rax, WPP_GLOBAL_Control
0x140078cc8  cmp     rcx, rax
0x140078ccb  jz      short loc_140078D2A
0x140078ccd  test    dword ptr [rcx+2Ch], 100h
0x140078cd4  jz      short loc_140078D2A
0x140078cd6  cmp     byte ptr [rcx+29h], 4
0x140078cda  jb      short loc_140078D2A
0x140078cdc  mov     rax, [rbx+60h]
0x140078ce0  test    rax, rax
0x140078ce3  jz      short loc_140078CEA
0x140078ce5  mov     rdx, [rax]
0x140078ce8  jmp     short loc_140078CEC
0x140078cea  xor     edx, edx
0x140078cec  mov     rax, [rbx+168h]
0x140078cf3  mov     r9, r13
0x140078cf6  mov     rcx, [rcx+18h]
0x140078cfa  mov     [rsp+0A8h+var_68], rax
0x140078cff  mov     rax, [rbx+160h]
0x140078d06  mov     [rsp+0A8h+var_70], rax
0x140078d0b  mov     rax, [rsp+0A8h+arg_0]
0x140078d13  mov     [rsp+0A8h+Index], rdx
0x140078d18  mov     [rsp+0A8h+SectorCountFromStartingLbn], rbx
0x140078d1d  mov     rax, [rax]
0x140078d20  mov     [rsp+0A8h+StartingLbn], rax
0x140078d25  call    WPP_SF_iqqqii
0x140078d2a  mov     rax, [rsp+0A8h+arg_28]
0x140078d32  mov     byte ptr [rax], 1
0x140078d35  jmp     loc_140078A62
```
