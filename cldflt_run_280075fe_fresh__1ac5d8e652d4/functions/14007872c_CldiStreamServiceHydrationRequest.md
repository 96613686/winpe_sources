# CldiStreamServiceHydrationRequest

- ea: `0x14007872c`
- end: `0x140078bfa`
- name: `CldiStreamServiceHydrationRequest`
- size: `1230`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x14006d078`
- `0x1400829e0`

## callees

- `0x140003c50`
- `0x140010de8`
- `0x140010e94`
- `0x140010fc4`
- `0x140011070`
- `0x14001112c`
- `0x14001e280`
- `0x14007872c`

## import_xrefs

- `ntoskrnl!FsRtlLookupBaseMcbEntry` at `0x1400788e7`
- `ntoskrnl!FsRtlLookupBaseMcbEntry` at `0x1400788e7`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x1400788a3`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x1400788a3`

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
0x14007872c  mov     r11, rsp
0x14007872f  mov     [r11+20h], rbx
0x140078733  mov     [r11+18h], r8
0x140078737  mov     [r11+8], rcx
0x14007873b  push    rbp
0x14007873c  push    rsi
0x14007873d  push    rdi
0x14007873e  push    r12
0x140078740  push    r13
0x140078742  push    r14
0x140078744  push    r15
0x140078746  sub     rsp, 70h
0x14007874a  mov     rax, [rcx]
0x14007874d  mov     r12, r9
0x140078750  mov     rdi, rdx
0x140078753  mov     r13, 7FFFFFFFFFFFFFFFh
0x14007875d  mov     r9, [rax]
0x140078760  mov     rax, [r9+10h]
0x140078764  mov     r15d, [r9+1Ch]
0x140078768  mov     r10, [rax+20h]
0x14007876c  mov     [rsp+0A8h+arg_8], r10
0x140078774  mov     qword ptr [r11-48h], 0
0x14007877c  mov     qword ptr [r11-40h], 0
0x140078784  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140078788  jz      short loc_14007878E
0x14007878a  lea     r13, [rdx+r8]
0x14007878e  mov     rbx, [rsp+0A8h+arg_20]
0x140078796  mov     rax, [rsp+0A8h+arg_30]
0x14007879e  mov     rbp, [rbx+160h]
0x1400787a5  mov     rcx, [rbx+168h]
0x1400787ac  test    rax, rax
0x1400787af  jz      short loc_1400787B4
0x1400787b1  mov     byte ptr [rax], 0
0x1400787b4  cmp     r13, rbp
0x1400787b7  jle     loc_14007893D
0x1400787bd  lea     r14, [rcx+rbp]
0x1400787c1  mov     [rsp+0A8h+arg_20], r14
0x1400787c9  cmp     r14, rdi
0x1400787cc  jle     loc_14007893D
0x1400787d2  not     r15d
0x1400787d5  and     r15d, 2
0x1400787d9  shl     r15, 0Bh
0x1400787dd  test    rax, rax
0x1400787e0  jz      short loc_1400787E5
0x1400787e2  mov     byte ptr [rax], 1
0x1400787e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400787ec  lea     rdx, WPP_GLOBAL_Control
0x1400787f3  cmp     rcx, rdx
0x1400787f6  jz      short loc_14007880B
0x1400787f8  test    dword ptr [rcx+2Ch], 100h
0x1400787ff  jz      short loc_14007880B
0x140078801  cmp     byte ptr [rcx+29h], 4
0x140078805  jnb     loc_140078953
0x14007880b  test    r12, r12
0x14007880e  jnz     loc_1400789B4
0x140078814  cmp     rbp, rdi
0x140078817  jg      loc_14007894C
0x14007881d  mov     rsi, rdi
0x140078820  sub     rsi, rbp
0x140078823  cmp     r13, r14
0x140078826  cmovl   r14, r13
0x14007882a  cmp     rdi, rbp
0x14007882d  cmovg   rbp, rdi
0x140078831  sub     r14, rbp
0x140078834  mov     rcx, cs:WPP_GLOBAL_Control
0x14007883b  lea     rax, WPP_GLOBAL_Control
0x140078842  cmp     rcx, rax
0x140078845  jz      short loc_14007885A
0x140078847  test    dword ptr [rcx+2Ch], 100h
0x14007884e  jz      short loc_14007885A
0x140078850  cmp     byte ptr [rcx+29h], 4
0x140078854  jnb     loc_140078A6C
0x14007885a  mov     r13, [rsp+0A8h+arg_8]
0x140078862  lea     rbp, [r15-1]
0x140078866  not     rbp
0x140078869  lea     r12, [rbx+130h]
0x140078870  mov     r8, rbp
0x140078873  mov     rcx, r12; Mcb
0x140078876  and     r8, rsi
0x140078879  mov     rax, r8
0x14007887c  cqo
0x14007887e  idiv    r15
0x140078881  mov     r10, rax
0x140078884  lea     rax, [r15-1]
0x140078888  add     rax, r14
0x14007888b  add     rax, rsi
0x14007888e  and     rax, rbp
0x140078891  sub     rax, r8
0x140078894  lea     r8, [r10+1]; Lbn
0x140078898  cqo
0x14007889a  idiv    r15
0x14007889d  mov     rdx, r10; Vbn
0x1400788a0  mov     r9, rax; SectorCount
0x1400788a3  call    cs:__imp_FsRtlAddBaseMcbEntry
0x1400788aa  nop     dword ptr [rax+rax+00h]
0x1400788af  xor     ecx, ecx
0x1400788b1  test    al, al
0x1400788b3  jz      loc_140078AD1
0x1400788b9  mov     rdi, [rbx+160h]
0x1400788c0  lea     r9, [rsp+0A8h+SectorCountFromLbn]; SectorCountFromLbn
0x1400788c5  mov     r14, [rbx+168h]
0x1400788cc  lea     r8, [rsp+0A8h+Lbn]; Lbn
0x1400788d1  mov     [rsp+0A8h+Index], rcx; Index
0x1400788d6  mov     esi, ecx
0x1400788d8  mov     [rsp+0A8h+SectorCountFromStartingLbn], rcx; SectorCountFromStartingLbn
0x1400788dd  xor     edx, edx; Vbn
0x1400788df  mov     [rsp+0A8h+StartingLbn], rcx; StartingLbn
0x1400788e4  mov     rcx, r12; Mcb
0x1400788e7  call    cs:__imp_FsRtlLookupBaseMcbEntry
0x1400788ee  nop     dword ptr [rax+rax+00h]
0x1400788f3  test    al, al
0x1400788f5  jz      short loc_140078922
0x1400788f7  cmp     [rsp+0A8h+Lbn], 0FFFFFFFFFFFFFFFFh
0x1400788fd  jz      short loc_140078922
0x1400788ff  lea     rax, [rdi-1]
0x140078903  add     rax, r14
0x140078906  add     rax, r15
0x140078909  and     rax, rbp
0x14007890c  and     rbp, rdi
0x14007890f  sub     rax, rbp
0x140078912  cqo
0x140078914  idiv    r15
0x140078917  cmp     [rsp+0A8h+SectorCountFromLbn], rax
0x14007891c  jge     loc_140078B7A
0x140078922  mov     rbx, [rsp+0A8h+arg_18]
0x14007892a  mov     eax, esi
0x14007892c  add     rsp, 70h
0x140078930  pop     r15
0x140078932  pop     r14
0x140078934  pop     r13
0x140078936  pop     r12
0x140078938  pop     rdi
0x140078939  pop     rsi
0x14007893a  pop     rbp
0x14007893b  retn
0x14007893d  mov     rcx, [rsp+0A8h+arg_28]
0x140078945  xor     esi, esi
0x140078947  mov     [rcx], sil
0x14007894a  jmp     short loc_140078922
0x14007894c  xor     esi, esi
0x14007894e  jmp     loc_140078823
0x140078953  mov     rax, [rbx+60h]
0x140078957  test    rax, rax
0x14007895a  jz      short loc_140078961
0x14007895c  mov     rdx, [rax]
0x14007895f  jmp     short loc_140078963
0x140078961  xor     edx, edx
0x140078963  mov     rax, [rbx+168h]
0x14007896a  mov     r9, r10
0x14007896d  mov     rcx, [rcx+18h]
0x140078971  mov     [rsp+0A8h+var_58], r12
0x140078976  mov     [rsp+0A8h+var_60], r8
0x14007897b  mov     [rsp+0A8h+var_68], rdi
0x140078980  mov     [rsp+0A8h+var_70], rax
0x140078985  mov     rax, [rbx+160h]
0x14007898c  mov     [rsp+0A8h+Index], rax
0x140078991  mov     [rsp+0A8h+SectorCountFromStartingLbn], rdx
0x140078996  mov     [rsp+0A8h+StartingLbn], rbx
0x14007899b  call    WPP_SF_iqqiiiiq
0x1400789a0  mov     r10, [rsp+0A8h+arg_8]
0x1400789a8  lea     rdx, WPP_GLOBAL_Control
0x1400789af  jmp     loc_14007880B
0x1400789b4  mov     rsi, [rbx+148h]
0x1400789bb  test    rsi, rsi
0x1400789be  jz      loc_140078814
0x1400789c4  mov     rcx, [rbx+150h]
0x1400789cb  movsxd  r14, dword ptr [rbx+158h]
0x1400789d2  add     r14, rcx
0x1400789d5  cmp     rcx, rdi
0x1400789d8  jg      short loc_1400789E2
0x1400789da  sub     rsi, rcx
0x1400789dd  add     rsi, rdi
0x1400789e0  jmp     short loc_1400789EB
0x1400789e2  mov     rax, rcx
0x1400789e5  sub     rax, rdi
0x1400789e8  add     r12, rax
0x1400789eb  cmp     r13, r14
0x1400789ee  cmovl   r14, r13
0x1400789f2  cmp     rdi, rcx
0x1400789f5  cmovg   rcx, rdi
0x1400789f9  sub     r14, rcx
0x1400789fc  test    r14, r14
0x1400789ff  jle     short loc_140078A5F
0x140078a01  mov     rcx, cs:WPP_GLOBAL_Control
0x140078a08  cmp     rcx, rdx
0x140078a0b  jz      short loc_140078A51
0x140078a0d  test    dword ptr [rcx+2Ch], 100h
0x140078a14  jz      short loc_140078A51
0x140078a16  cmp     byte ptr [rcx+29h], 4
0x140078a1a  jb      short loc_140078A51
0x140078a1c  mov     rax, [rbx+60h]
0x140078a20  test    rax, rax
0x140078a23  jz      short loc_140078A2A
0x140078a25  mov     rdx, [rax]
0x140078a28  jmp     short loc_140078A2C
0x140078a2a  xor     edx, edx
0x140078a2c  mov     rcx, [rcx+18h]
0x140078a30  mov     r9, r10
0x140078a33  mov     [rsp+0A8h+var_68], r14
0x140078a38  mov     [rsp+0A8h+var_70], r12
0x140078a3d  mov     [rsp+0A8h+Index], rsi
0x140078a42  mov     [rsp+0A8h+SectorCountFromStartingLbn], rdx
0x140078a47  mov     [rsp+0A8h+StartingLbn], rbx
0x140078a4c  call    WPP_SF_iqqqqi
0x140078a51  mov     r8, r14; Size
0x140078a54  mov     rdx, r12; Src
0x140078a57  mov     rcx, rsi; void *
0x140078a5a  call    memmove
0x140078a5f  mov     r14, [rsp+0A8h+arg_20]
0x140078a67  jmp     loc_140078814
0x140078a6c  mov     rax, [rbx+60h]
0x140078a70  test    rax, rax
0x140078a73  jz      short loc_140078A7A
0x140078a75  mov     rdx, [rax]
0x140078a78  jmp     short loc_140078A7C
0x140078a7a  xor     edx, edx
0x140078a7c  mov     rax, [rbx+168h]
0x140078a83  mov     r13, [rsp+0A8h+arg_8]
0x140078a8b  mov     rcx, [rcx+18h]
0x140078a8f  mov     r9, r13
0x140078a92  mov     [rsp+0A8h+var_58], r14
0x140078a97  mov     [rsp+0A8h+var_60], rsi
0x140078a9c  mov     [rsp+0A8h+var_68], rax
0x140078aa1  mov     rax, [rbx+160h]
0x140078aa8  mov     [rsp+0A8h+var_70], rax
0x140078aad  mov     rax, [rsp+0A8h+arg_0]
0x140078ab5  mov     [rsp+0A8h+Index], rdx
0x140078aba  mov     [rsp+0A8h+SectorCountFromStartingLbn], rbx
0x140078abf  mov     rax, [rax]
0x140078ac2  mov     [rsp+0A8h+StartingLbn], rax
0x140078ac7  call    WPP_SF_iqqqiiii
0x140078acc  jmp     loc_140078862
0x140078ad1  mov     esi, 0C000009Ah
0x140078ad6  mov     ecx, esi
0x140078ad8  call    HsmDbgBreakOnStatus
0x140078add  mov     rcx, cs:WPP_GLOBAL_Control
0x140078ae4  lea     rax, WPP_GLOBAL_Control
0x140078aeb  cmp     rcx, rax
0x140078aee  jz      loc_140078922
0x140078af4  test    dword ptr [rcx+2Ch], 100h
0x140078afb  jz      loc_140078922
0x140078b01  cmp     byte ptr [rcx+29h], 3
0x140078b05  jb      loc_140078922
0x140078b0b  mov     rax, [rbx+60h]
0x140078b0f  test    rax, rax
0x140078b12  jz      short loc_140078B19
0x140078b14  mov     r8, [rax]
0x140078b17  jmp     short loc_140078B1C
0x140078b19  xor     r8d, r8d
0x140078b1c  mov     rax, [rsp+0A8h+arg_10]
0x140078b24  mov     edx, 1Ah
0x140078b29  mov     rcx, [rcx+18h]
0x140078b2d  mov     r9, r13
0x140078b30  mov     [rsp+0A8h+var_50], esi
0x140078b34  mov     [rsp+0A8h+var_58], rax
0x140078b39  mov     rax, [rbx+168h]
0x140078b40  mov     [rsp+0A8h+var_60], rdi
0x140078b45  mov     [rsp+0A8h+var_68], rax
0x140078b4a  mov     rax, [rbx+160h]
0x140078b51  mov     [rsp+0A8h+var_70], rax
0x140078b56  mov     rax, [rsp+0A8h+arg_0]
0x140078b5e  mov     [rsp+0A8h+Index], r8
0x140078b63  mov     [rsp+0A8h+SectorCountFromStartingLbn], rbx
0x140078b68  mov     rax, [rax]
0x140078b6b  mov     [rsp+0A8h+StartingLbn], rax
0x140078b70  call    WPP_SF_iqqqiiiid
0x140078b75  jmp     loc_140078922
0x140078b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140078b81  lea     rax, WPP_GLOBAL_Control
0x140078b88  cmp     rcx, rax
0x140078b8b  jz      short loc_140078BEA
0x140078b8d  test    dword ptr [rcx+2Ch], 100h
0x140078b94  jz      short loc_140078BEA
0x140078b96  cmp     byte ptr [rcx+29h], 4
0x140078b9a  jb      short loc_140078BEA
0x140078b9c  mov     rax, [rbx+60h]
0x140078ba0  test    rax, rax
0x140078ba3  jz      short loc_140078BAA
0x140078ba5  mov     rdx, [rax]
0x140078ba8  jmp     short loc_140078BAC
0x140078baa  xor     edx, edx
0x140078bac  mov     rax, [rbx+168h]
0x140078bb3  mov     r9, r13
0x140078bb6  mov     rcx, [rcx+18h]
0x140078bba  mov     [rsp+0A8h+var_68], rax
0x140078bbf  mov     rax, [rbx+160h]
0x140078bc6  mov     [rsp+0A8h+var_70], rax
0x140078bcb  mov     rax, [rsp+0A8h+arg_0]
0x140078bd3  mov     [rsp+0A8h+Index], rdx
0x140078bd8  mov     [rsp+0A8h+SectorCountFromStartingLbn], rbx
0x140078bdd  mov     rax, [rax]
0x140078be0  mov     [rsp+0A8h+StartingLbn], rax
0x140078be5  call    WPP_SF_iqqqii
0x140078bea  mov     rax, [rsp+0A8h+arg_28]
0x140078bf2  mov     byte ptr [rax], 1
0x140078bf5  jmp     loc_140078922
```
