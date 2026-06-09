# DfscFsctrlCreateDriveLetter

- ea: `0x140029160`
- end: `0x140029a6c`
- name: `DfscFsctrlCreateDriveLetter`
- size: `2316`
- prototype: `__int64 __fastcall(__int64, char *, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x140014910`

## callees

- `0x140001010`
- `0x140002340`
- `0x140002570`
- `0x1400025a0`
- `0x1400027f8`
- `0x1400028f4`
- `0x140004554`
- `0x1400045ec`
- `0x140005f70`
- `0x14001338c`
- `0x14001433c`
- `0x1400187e4`
- `0x14001ef20`
- `0x140021c10`
- `0x1400221cc`
- `0x140024ec0`
- `0x140024ff0`
- `0x1400252b0`
- `0x1400281ac`
- `0x140029160`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140029335`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140029335`
- `ntoskrnl!towupper` at `0x1400292f5`
- `ntoskrnl!towupper` at `0x140029316`
- `ntoskrnl!towupper` at `0x1400292f5`
- `ntoskrnl!towupper` at `0x140029316`

## pseudocode

```c
__int64 __fastcall DfscFsctrlCreateDriveLetter(__int64 a1, char *a2, int a3)
{
  unsigned __int16 v3; // r13
  int v6; // edx
  int v7; // r11d
  unsigned __int64 v8; // r10
  __int64 v9; // r9
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  unsigned int ContainerContextFromIrp; // ebx
  __int64 v14; // r9
  unsigned int v15; // esi
  wint_t *v16; // rbx
  wint_t v17; // cx
  wint_t v18; // ax
  int v19; // r14d
  unsigned int v20; // r10d
  unsigned int v21; // ecx
  int v22; // esi
  wint_t *v23; // r15
  unsigned int v24; // r12d
  wint_t *v25; // r8
  unsigned int v26; // ecx
  unsigned int AuthIdentityLength; // r12d
  __int16 v28; // ax
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // r9
  PDEVICE_OBJECT v32; // rcx
  __int64 v33; // rdx
  unsigned int v34; // edx
  unsigned __int64 v35; // rax
  wint_t *v36; // r11
  unsigned int v37; // ecx
  unsigned int v38; // edx
  wint_t *v39; // r13
  unsigned __int16 v40; // r14
  int v41; // r8d
  ULONG_PTR v42; // r14
  bool v43; // zf
  unsigned int ExplicitCredentials; // eax
  char v45; // r12
  __int64 v46; // rbx
  int v47; // r15d
  unsigned int v48; // esi
  unsigned __int16 v49; // dx
  int v50; // edi
  PDEVICE_OBJECT v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // r9
  struct _UNICODE_STRING *p_DestinationString; // r12
  int v55; // edx
  int v56; // r8d
  unsigned __int16 v58; // [rsp+50h] [rbp-B0h]
  int v59; // [rsp+54h] [rbp-ACh]
  unsigned int v60; // [rsp+58h] [rbp-A8h]
  ULONG_PTR BugCheckParameter3; // [rsp+60h] [rbp-A0h] BYREF
  wint_t *v62; // [rsp+68h] [rbp-98h]
  __int64 v63; // [rsp+70h] [rbp-90h] BYREF
  __int128 v64; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v65; // [rsp+88h] [rbp-78h]
  wint_t *v66; // [rsp+90h] [rbp-70h]
  char *v67; // [rsp+98h] [rbp-68h]
  __int64 v68; // [rsp+A0h] [rbp-60h]
  char *AuthIdentityByteArray; // [rsp+A8h] [rbp-58h]
  int v70; // [rsp+B0h] [rbp-50h] BYREF
  int v71; // [rsp+B4h] [rbp-4Ch]
  wint_t *v72; // [rsp+B8h] [rbp-48h]
  int v73[4]; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-30h] BYREF
  int v75[4]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v76[4]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v77; // [rsp+130h] [rbp+30h]
  WCHAR SourceString; // [rsp+140h] [rbp+40h] BYREF
  int v79; // [rsp+142h] [rbp+42h]

  v68 = a1;
  v3 = 0;
  BugCheckParameter3 = 0;
  v71 = 0;
  v63 = 0;
  DestinationString = 0;
  *(_OWORD *)v73 = 0;
  v64 = 0;
  *(_OWORD *)v75 = 0;
  memset(v76, 0, sizeof(v76));
  v77 = 0;
  if ( (unsigned int)a3 < 0x18 )
    return (unsigned int)-1073741811;
  if ( (a3 & 1) != 0 )
    return (unsigned int)-1073741811;
  if ( a3 < 0 )
    return (unsigned int)-1073741811;
  if ( !a2 )
    return (unsigned int)-1073741811;
  v6 = *((unsigned __int16 *)a2 + 5);
  if ( !(_WORD)v6 )
    return (unsigned int)-1073741811;
  v7 = *((unsigned __int16 *)a2 + 4);
  if ( (((unsigned __int16)v6 | (unsigned __int16)v7) & 1) != 0 )
    return (unsigned int)-1073741811;
  v8 = *((unsigned __int16 *)a2 + 6);
  if ( (v8 & 1) != 0 )
    return (unsigned int)-1073741811;
  v9 = *((unsigned __int16 *)a2 + 7);
  if ( (v9 & 1) != 0 )
    return (unsigned int)-1073741811;
  v10 = *((unsigned __int16 *)a2 + 8);
  if ( (v10 & 1) != 0 )
    return (unsigned int)-1073741811;
  if ( (_WORD)v7 == 0xFFFF )
    return (unsigned int)-1073741811;
  if ( (_WORD)v6 == 0xFFFF )
    return (unsigned int)-1073741811;
  if ( (_WORD)v8 == 0xFFFF )
    return (unsigned int)-1073741811;
  if ( (_WORD)v9 == 0xFFFF )
    return (unsigned int)-1073741811;
  if ( (_WORD)v10 == 0xFFFF )
    return (unsigned int)-1073741811;
  v11 = v8 + v10;
  v12 = *((unsigned __int16 *)a2 + 10);
  v65 = a3 - 22;
  if ( (unsigned int)*((unsigned __int16 *)a2 + 9) + v12 + v6 + v7 + v11 > a3 - 22 || (_WORD)v9 && v9 + 2 >= v8 )
    return (unsigned int)-1073741811;
  ContainerContextFromIrp = DfscGetContainerContextFromIrp(a1, &v63);
  if ( (ContainerContextFromIrp & 0x80000000) != 0 )
    return ContainerContextFromIrp;
  v15 = *((unsigned __int16 *)a2 + 4);
  v16 = (wint_t *)(a2 + 22);
  if ( (_WORD)v15 )
  {
    if ( *((_WORD *)a2 + 12) != 58 || *((_WORD *)a2 + 13) || (unsigned __int16)(towupper(*v16) - 65) > 0x19u )
      return (unsigned int)-1073741634;
    v17 = *v16;
    v67 = a2 + 22;
    v18 = towupper(v17);
    v79 = 58;
    SourceString = v18;
    RtlInitUnicodeStringEx(&DestinationString, &SourceString);
  }
  else
  {
    v67 = 0;
  }
  v19 = *((unsigned __int16 *)a2 + 5);
  v20 = v15;
  v60 = v15;
  v59 = 0;
  AuthIdentityByteArray = 0;
  v21 = v19 + v15;
  v66 = 0;
  v22 = *((unsigned __int16 *)a2 + 6);
  if ( (_WORD)v22 )
    v23 = &v16[(unsigned __int64)v21 >> 1];
  else
    v23 = 0;
  v24 = v22 + v21;
  v58 = *((_WORD *)a2 + 8);
  if ( v58 )
  {
    v25 = &v16[(unsigned __int64)v24 >> 1];
    v62 = v25;
    if ( v23 )
    {
      v59 = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids);
        v25 = v62;
        v20 = v60;
      }
    }
    v3 = v58;
    goto LABEL_34;
  }
  v58 = 0;
  v25 = 0;
  if ( v23 )
  {
    if ( v22 != 2 )
      goto LABEL_34;
    if ( (a2[2] & 2) == 0 )
      goto LABEL_34;
    v59 = 1;
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0 )
    {
      goto LABEL_34;
    }
    v33 = 18;
  }
  else
  {
    v59 = 2;
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0 )
    {
      goto LABEL_34;
    }
    v33 = 17;
  }
  WPP_SF_(v32->AttachedDevice, v33, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids);
  v20 = v60;
  v25 = 0;
LABEL_34:
  v26 = v24 + v3;
  AuthIdentityLength = *((unsigned __int16 *)a2 + 9);
  if ( *((_WORD *)a2 + 9) )
  {
    v59 = 1;
    AuthIdentityByteArray = (char *)&v16[(unsigned __int64)v26 >> 1];
  }
  v28 = *((_WORD *)a2 + 10);
  if ( !v28 )
    goto LABEL_69;
  if ( v28 != 16 )
  {
    ContainerContextFromIrp = -1073741811;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      v30 = 19;
LABEL_41:
      v31 = 3221225485LL;
LABEL_42:
      WPP_SF_D(v29->AttachedDevice, v30, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids, v31);
      return ContainerContextFromIrp;
    }
    return ContainerContextFromIrp;
  }
  v34 = ((v26 + AuthIdentityLength + 37) & 0xFFFFFFF0) - 22;
  v35 = (unsigned __int64)v34 >> 1;
  v14 = *(unsigned int *)&v16[v35 + 4];
  v36 = &v16[v35];
  v66 = v36;
  if ( (_DWORD)v14 )
  {
    ContainerContextFromIrp = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids);
    }
    return ContainerContextFromIrp;
  }
  v37 = v34 + *(_DWORD *)v36;
  if ( v37 < v34 )
  {
    ContainerContextFromIrp = -1073741675;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      v30 = 21;
      v31 = 3221225621LL;
      goto LABEL_42;
    }
    return ContainerContextFromIrp;
  }
  v38 = v37 + *((_DWORD *)v36 + 1);
  if ( v38 < v37 )
  {
    ContainerContextFromIrp = -1073741675;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      v30 = 22;
      v31 = 3221225621LL;
      goto LABEL_42;
    }
    return ContainerContextFromIrp;
  }
  if ( v38 <= v65 )
  {
LABEL_69:
    v72 = v23;
    HIWORD(v70) = v22;
    v39 = &v16[(unsigned __int64)v20 >> 1];
    if ( (_WORD)v22 )
      LOWORD(v70) = v22 - 2;
    else
      LOWORD(v70) = 0;
    WORD1(v64) = v19;
    v40 = v19 - 2;
    *(_QWORD *)&v73[2] = v25;
    HIWORD(v73[0]) = v58;
    LOWORD(v73[0]) = v58;
    *((_QWORD *)&v64 + 1) = &v16[(unsigned __int64)v20 >> 1];
    LOWORD(v64) = v40;
    if ( v40 >= 4u && *v39 == 92 && v39[1] == 92 )
    {
      if ( v39 )
      {
        *((_QWORD *)&v64 + 1) = v39 + 1;
        LOWORD(v64) = v40 - 2;
        WORD1(v64) = v40;
      }
      if ( !(unsigned int)DfscInitDfsPath(&v64, v75, v25, v14)
        && LOWORD(v75[0])
        && LOWORD(v76[0])
        && (unsigned __int16)v77 >= 2u
        && **((_WORD **)&v77 + 1) == 92 )
      {
        if ( (unsigned __int8)DfscIsReservedShare(v76) )
        {
          ContainerContextFromIrp = -1073741634;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
          {
            WPP_SF_DZ(
              WPP_GLOBAL_Control->AttachedDevice,
              24,
              (unsigned int)WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids,
              -1073741634,
              (__int64)v76);
          }
          return ContainerContextFromIrp;
        }
        if ( v59 == 2 )
        {
          ContainerContextFromIrp = DfscCredCreateKeymgrCredentials(v75, 0, &BugCheckParameter3);
          v42 = BugCheckParameter3;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              25,
              WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids,
              BugCheckParameter3,
              ContainerContextFromIrp);
          }
          v43 = ContainerContextFromIrp == 0;
        }
        else
        {
          ExplicitCredentials = DfscCredCreateExplicitCredentials(
                                  (int)&v70,
                                  *((unsigned __int16 *)a2 + 7),
                                  (int)v73,
                                  (int)v75,
                                  *((_DWORD *)a2 + 1),
                                  AuthIdentityByteArray,
                                  AuthIdentityLength,
                                  v59 == 1,
                                  *((unsigned __int16 *)a2 + 1),
                                  (__int64)&BugCheckParameter3);
          v42 = BugCheckParameter3;
          ContainerContextFromIrp = ExplicitCredentials;
          v43 = ExplicitCredentials == 0;
        }
        if ( !v43 )
          goto LABEL_128;
        v45 = *a2;
        v46 = (__int64)v66;
        v47 = (*a2 != 0) + 1;
        if ( (a2[2] & 8) != 0 )
          v48 = -1073741634;
        else
          v48 = DfscCredVerify(v68, v63, (unsigned int)&v64, v42, (__int64)v66);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
        {
          WPP_SF_DZDD(
            WPP_GLOBAL_Control->AttachedDevice,
            *((unsigned __int16 *)a2 + 1),
            v41,
            v48,
            (__int64)&v64,
            *((_WORD *)a2 + 1),
            (v45 != 0) + 1);
        }
        if ( v48 )
        {
          if ( !(unsigned __int8)DfscIsErrorInList(v48, DfscFsctlPathTryCscErrorList, 8) || v45 )
            goto LABEL_123;
          v47 = 3;
        }
        v49 = *((_WORD *)a2 + 1);
        v50 = (v49 >> 4) & 2 | 4;
        if ( (v49 & 0x40) == 0 )
          v50 = (v49 >> 4) & 2;
        if ( v50 && !v67 )
        {
          ContainerContextFromIrp = -1073741311;
          v51 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
          {
            v52 = 27;
            v53 = 3221225985LL;
LABEL_110:
            WPP_SF_D(v51->AttachedDevice, v52, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids, v53);
            goto LABEL_128;
          }
          goto LABEL_128;
        }
        if ( (v49 & 0x80u) != 0 )
        {
          ContainerContextFromIrp = -1073741637;
          v51 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
          {
            v52 = 28;
            v53 = 3221225659LL;
            goto LABEL_110;
          }
LABEL_128:
          if ( v42 )
            DfscCredRelease(v42);
          return ContainerContextFromIrp;
        }
        p_DestinationString = &DestinationString;
        if ( !v67 )
          LODWORD(p_DestinationString) = 0;
        ContainerContextFromIrp = DfscCreateNetUseConnection(
                                    v63,
                                    v68,
                                    (_DWORD)p_DestinationString,
                                    (unsigned int)v75,
                                    v42,
                                    v47,
                                    v50,
                                    0,
                                    v46);
        if ( !ContainerContextFromIrp )
        {
          if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.DeviceObject & 4) == 0 )
            DfscReadLinkedConnectionPolicy();
          if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.DeviceObject & 2) != 0 )
            DfscCreateLinkedConnection(
              v63,
              v68,
              (_DWORD)p_DestinationString,
              (unsigned int)v75,
              v42,
              (__int64)v73,
              v47,
              v50);
          goto LABEL_128;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
        {
          WPP_SF_DS(WPP_GLOBAL_Control->AttachedDevice, v55, v56, ContainerContextFromIrp, (__int64)v39);
        }
        if ( !v48 || v47 == 3 )
          goto LABEL_128;
LABEL_123:
        ContainerContextFromIrp = v48;
        goto LABEL_128;
      }
      return (unsigned int)-1073741634;
    }
    return (unsigned int)-1073741811;
  }
  ContainerContextFromIrp = -1073741811;
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
  {
    v30 = 23;
    goto LABEL_41;
  }
  return ContainerContextFromIrp;
}

```

## disassembly

```asm
0x140029160  mov     [rsp-8+arg_10], rbx
0x140029165  push    rbp
0x140029166  push    rsi
0x140029167  push    rdi
0x140029168  push    r12
0x14002916a  push    r13
0x14002916c  push    r14
0x14002916e  push    r15
0x140029170  lea     rbp, [rsp-50h]
0x140029175  sub     rsp, 150h
0x14002917c  mov     rax, cs:__security_cookie
0x140029183  xor     rax, rsp
0x140029186  mov     [rbp+80h+var_38], rax
0x14002918a  xorps   xmm0, xmm0
0x14002918d  mov     [rbp+80h+var_E0], rcx
0x140029191  xor     r13d, r13d
0x140029194  xorps   xmm1, xmm1
0x140029197  mov     [rsp+180h+BugCheckParameter3], r13
0x14002919c  mov     rdi, rdx
0x14002919f  mov     [rbp+80h+var_CC], r13d
0x1400291a3  mov     rbx, rcx
0x1400291a6  mov     [rsp+180h+var_110], r13
0x1400291ab  movups  xmmword ptr [rbp+80h+DestinationString.Length], xmm0
0x1400291af  movups  xmmword ptr [rbp+80h+var_C0], xmm0
0x1400291b3  movups  [rsp+180h+var_108], xmm1
0x1400291b8  movups  xmmword ptr [rbp+80h+var_A0], xmm0
0x1400291bc  movups  [rbp+80h+var_90], xmm0
0x1400291c0  movups  [rbp+80h+var_80], xmm0
0x1400291c4  movups  [rbp+80h+var_70], xmm0
0x1400291c8  movups  [rbp+80h+var_60], xmm0
0x1400291cc  movups  [rbp+80h+var_50], xmm0
0x1400291d0  cmp     r8d, 18h
0x1400291d4  jb      loc_140029A3D
0x1400291da  test    r8b, 1
0x1400291de  jnz     loc_140029A3D
0x1400291e4  test    r8d, r8d
0x1400291e7  js      loc_140029A3D
0x1400291ed  test    rdx, rdx
0x1400291f0  jz      loc_140029A3D
0x1400291f6  movzx   edx, word ptr [rdx+0Ah]
0x1400291fa  test    dx, dx
0x1400291fd  jz      loc_140029A3D
0x140029203  movzx   r11d, word ptr [rdi+8]
0x140029208  movzx   ecx, r11w
0x14002920c  or      cx, dx
0x14002920f  bt      cx, r13w
0x140029214  jb      loc_140029A3D
0x14002921a  movzx   r10d, word ptr [rdi+0Ch]
0x14002921f  test    r10b, 1
0x140029223  jnz     loc_140029A3D
0x140029229  movzx   r9d, word ptr [rdi+0Eh]
0x14002922e  test    r9b, 1
0x140029232  jnz     loc_140029A3D
0x140029238  movzx   eax, word ptr [rdi+10h]
0x14002923c  test    al, 1
0x14002923e  jnz     loc_140029A3D
0x140029244  mov     ecx, 0FFFEh
0x140029249  cmp     r11w, cx
0x14002924d  ja      loc_140029A3D
0x140029253  cmp     dx, cx
0x140029256  ja      loc_140029A3D
0x14002925c  cmp     r10w, cx
0x140029260  ja      loc_140029A3D
0x140029266  cmp     r9w, cx
0x14002926a  ja      loc_140029A3D
0x140029270  cmp     ax, cx
0x140029273  ja      loc_140029A3D
0x140029279  lea     ecx, [r10+rax]
0x14002927d  add     r8d, 0FFFFFFEAh
0x140029281  movzx   eax, word ptr [rdi+14h]
0x140029285  add     ecx, r11d
0x140029288  add     ecx, edx
0x14002928a  mov     [rbp+80h+var_F8], r8d
0x14002928e  add     ecx, eax
0x140029290  movzx   eax, word ptr [rdi+12h]
0x140029294  add     ecx, eax
0x140029296  cmp     ecx, r8d
0x140029299  ja      loc_140029A3D
0x14002929f  test    r9w, r9w
0x1400292a3  jz      short loc_1400292B2
0x1400292a5  lea     rcx, [r9+2]
0x1400292a9  cmp     rcx, r10
0x1400292ac  jnb     loc_140029A3D
0x1400292b2  lea     rdx, [rsp+180h+var_110]
0x1400292b7  mov     rcx, rbx
0x1400292ba  call    DfscGetContainerContextFromIrp
0x1400292bf  mov     ebx, eax
0x1400292c1  test    eax, eax
0x1400292c3  js      loc_140029A42
0x1400292c9  movzx   esi, word ptr [rdi+8]
0x1400292cd  lea     rbx, [rdi+16h]
0x1400292d1  test    si, si
0x1400292d4  jnz     short loc_1400292DC
0x1400292d6  mov     [rbp+80h+var_E8], r13
0x1400292da  jmp     short loc_140029341
0x1400292dc  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1400292e1  jnz     loc_140029A36
0x1400292e7  cmp     [rbx+4], r13w
0x1400292ec  jnz     loc_140029A36
0x1400292f2  movzx   ecx, word ptr [rbx]; C
0x1400292f5  call    cs:__imp_towupper
0x1400292fc  nop     dword ptr [rax+rax+00h]
0x140029301  sub     ax, 41h ; 'A'
0x140029305  cmp     ax, 19h
0x140029309  ja      loc_140029A36
0x14002930f  movzx   ecx, word ptr [rbx]; C
0x140029312  mov     [rbp+80h+var_E8], rbx
0x140029316  call    cs:__imp_towupper
0x14002931d  nop     dword ptr [rax+rax+00h]
0x140029322  lea     rdx, [rbp+80h+SourceString]; SourceString
0x140029326  mov     [rbp+80h+var_3E], 3Ah ; ':'
0x14002932d  lea     rcx, [rbp+80h+DestinationString]; DestinationString
0x140029331  mov     [rbp+80h+SourceString], ax
0x140029335  call    cs:__imp_RtlInitUnicodeStringEx
0x14002933c  nop     dword ptr [rax+rax+00h]
0x140029341  movzx   r14d, word ptr [rdi+0Ah]
0x140029346  mov     r10d, esi
0x140029349  mov     [rsp+180h+var_128], esi
0x14002934d  mov     [rsp+180h+var_12C], r13d
0x140029352  mov     [rbp+80h+var_D8], r13
0x140029356  lea     ecx, [r14+rsi]
0x14002935a  mov     [rbp+80h+var_F0], r13
0x14002935e  movzx   esi, word ptr [rdi+0Ch]
0x140029362  test    si, si
0x140029365  jz      short loc_140029372
0x140029367  mov     eax, ecx
0x140029369  shr     rax, 1
0x14002936c  lea     r15, [rbx+rax*2]
0x140029370  jmp     short loc_140029375
0x140029372  mov     r15, r13
0x140029375  mov     eax, esi
0x140029377  lea     r12d, [rsi+rcx]
0x14002937b  movzx   eax, word ptr [rdi+10h]
0x14002937f  lea     rdx, WPP_GLOBAL_Control
0x140029386  mov     [rsp+180h+var_130], eax
0x14002938a  test    ax, ax
0x14002938d  jz      loc_14002946E
0x140029393  mov     eax, r12d
0x140029396  shr     rax, 1
0x140029399  lea     r8, [rbx+rax*2]
0x14002939d  mov     [rsp+180h+var_118], r8
0x1400293a2  test    r15, r15
0x1400293a5  jz      short loc_1400293EA
0x1400293a7  mov     [rsp+180h+var_12C], 1
0x1400293af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400293b6  cmp     rcx, rdx
0x1400293b9  jz      short loc_1400293EA
0x1400293bb  test    dword ptr [rcx+2Ch], 400000h
0x1400293c2  jz      short loc_1400293EA
0x1400293c4  mov     rcx, [rcx+18h]
0x1400293c8  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x1400293cf  mov     edx, 10h
0x1400293d4  call    WPP_SF_
0x1400293d9  mov     r8, [rsp+180h+var_118]
0x1400293de  lea     rdx, WPP_GLOBAL_Control
0x1400293e5  mov     r10d, [rsp+180h+var_128]
0x1400293ea  mov     r13d, [rsp+180h+var_130]
0x1400293ef  movzx   ecx, r13w
0x1400293f3  add     ecx, r12d
0x1400293f6  movzx   r12d, word ptr [rdi+12h]
0x1400293fb  test    r12d, r12d
0x1400293fe  jz      short loc_140029415
0x140029400  mov     eax, ecx
0x140029402  shr     rax, 1
0x140029405  mov     [rsp+180h+var_12C], 1
0x14002940d  lea     rax, [rbx+rax*2]
0x140029411  mov     [rbp+80h+var_D8], rax
0x140029415  movzx   eax, word ptr [rdi+14h]
0x140029419  test    ax, ax
0x14002941c  jz      loc_140029634
0x140029422  cmp     ax, 10h
0x140029426  jz      loc_140029508
0x14002942c  mov     ebx, 0C000000Dh
0x140029431  mov     rcx, cs:WPP_GLOBAL_Control
0x140029438  cmp     rcx, rdx
0x14002943b  jz      loc_140029A42
0x140029441  test    dword ptr [rcx+2Ch], 400000h
0x140029448  jz      loc_140029A42
0x14002944e  mov     edx, 13h
0x140029453  mov     r9d, 0C000000Dh
0x140029459  mov     rcx, [rcx+18h]
0x14002945d  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x140029464  call    WPP_SF_D
0x140029469  jmp     loc_140029A42
0x14002946e  mov     [rsp+180h+var_130], r13d
0x140029473  mov     r8, r13
0x140029476  test    r15, r15
0x140029479  jnz     short loc_1400294C9
0x14002947b  mov     [rsp+180h+var_12C], 2
0x140029483  mov     rcx, cs:WPP_GLOBAL_Control
0x14002948a  cmp     rcx, rdx
0x14002948d  jz      loc_1400293EF
0x140029493  test    dword ptr [rcx+2Ch], 400000h
0x14002949a  jz      loc_1400293EF
0x1400294a0  mov     edx, 11h
0x1400294a5  mov     rcx, [rcx+18h]
0x1400294a9  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x1400294b0  call    WPP_SF_
0x1400294b5  mov     r10d, [rsp+180h+var_128]
0x1400294ba  lea     rdx, WPP_GLOBAL_Control
0x1400294c1  mov     r8, r13
0x1400294c4  jmp     loc_1400293EF
0x1400294c9  cmp     esi, 2
0x1400294cc  jnz     loc_1400293EF
0x1400294d2  test    [rdi+2], sil
0x1400294d6  jz      loc_1400293EF
0x1400294dc  mov     [rsp+180h+var_12C], 1
0x1400294e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400294eb  cmp     rcx, rdx
0x1400294ee  jz      loc_1400293EF
0x1400294f4  test    dword ptr [rcx+2Ch], 400000h
0x1400294fb  jz      loc_1400293EF
0x140029501  mov     edx, 12h
0x140029506  jmp     short loc_1400294A5
0x140029508  lea     edx, [r12+25h]
0x14002950d  add     edx, ecx
0x14002950f  and     edx, 0FFFFFFF0h
0x140029512  add     edx, 0FFFFFFEAh
0x140029515  mov     eax, edx
0x140029517  shr     rax, 1
0x14002951a  mov     r9d, [rbx+rax*2+8]
0x14002951f  lea     r11, [rbx+rax*2]
0x140029523  mov     [rbp+80h+var_F0], r11
0x140029527  test    r9d, r9d
0x14002952a  jz      short loc_140029577
0x14002952c  mov     ebx, 0C000000Dh
0x140029531  mov     rcx, cs:WPP_GLOBAL_Control
0x140029538  lea     rax, WPP_GLOBAL_Control
0x14002953f  cmp     rcx, rax
0x140029542  jz      loc_140029A42
0x140029548  test    dword ptr [rcx+2Ch], 400000h
0x14002954f  jz      loc_140029A42
0x140029555  mov     rcx, [rcx+18h]
0x140029559  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x140029560  mov     edx, 14h
0x140029565  mov     [rsp+180h+var_160], 0C000000Dh
0x14002956d  call    WPP_SF_dd
0x140029572  jmp     loc_140029A42
0x140029577  mov     ecx, [r11]
0x14002957a  add     ecx, edx
0x14002957c  cmp     ecx, edx
0x14002957e  jnb     short loc_1400295B9
0x140029580  mov     ebx, 0C0000095h
0x140029585  mov     rcx, cs:WPP_GLOBAL_Control
0x14002958c  lea     rax, WPP_GLOBAL_Control
0x140029593  cmp     rcx, rax
0x140029596  jz      loc_140029A42
0x14002959c  test    dword ptr [rcx+2Ch], 400000h
0x1400295a3  jz      loc_140029A42
0x1400295a9  mov     edx, 15h
0x1400295ae  mov     r9d, 0C0000095h
0x1400295b4  jmp     loc_140029459
0x1400295b9  mov     edx, [r11+4]
0x1400295bd  add     edx, ecx
0x1400295bf  cmp     edx, ecx
0x1400295c1  jnb     short loc_1400295FC
0x1400295c3  mov     ebx, 0C0000095h
0x1400295c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400295cf  lea     rax, WPP_GLOBAL_Control
0x1400295d6  cmp     rcx, rax
0x1400295d9  jz      loc_140029A42
0x1400295df  test    dword ptr [rcx+2Ch], 400000h
0x1400295e6  jz      loc_140029A42
0x1400295ec  mov     edx, 16h
0x1400295f1  mov     r9d, 0C0000095h
0x1400295f7  jmp     loc_140029459
0x1400295fc  cmp     edx, [rbp+80h+var_F8]
0x1400295ff  jbe     short loc_140029634
0x140029601  mov     ebx, 0C000000Dh
0x140029606  mov     rcx, cs:WPP_GLOBAL_Control
0x14002960d  lea     rax, WPP_GLOBAL_Control
0x140029614  cmp     rcx, rax
0x140029617  jz      loc_140029A42
0x14002961d  test    dword ptr [rcx+2Ch], 400000h
0x140029624  jz      loc_140029A42
0x14002962a  mov     edx, 17h
0x14002962f  jmp     loc_140029453
0x140029634  mov     eax, r10d
0x140029637  shr     rax, 1
0x14002963a  mov     [rbp+80h+var_C8], r15
0x14002963e  mov     word ptr [rbp+80h+var_D0+2], si
0x140029642  lea     r13, [rbx+rax*2]
0x140029646  test    si, si
0x140029649  jnz     short loc_140029653
0x14002964b  xor     eax, eax
0x14002964d  mov     word ptr [rbp+80h+var_D0], ax
0x140029651  jmp     short loc_14002965B
0x140029653  sub     si, 2
0x140029657  mov     word ptr [rbp+80h+var_D0], si
0x14002965b  mov     eax, [rsp+180h+var_130]
0x14002965f  mov     word ptr [rsp+180h+var_108+2], r14w
0x140029665  sub     r14w, 2
0x14002966a  mov     qword ptr [rbp+80h+var_C0+8], r8
0x14002966e  mov     word ptr [rbp+80h+var_C0+2], ax
0x140029672  mov     word ptr [rbp+80h+var_C0], ax
0x140029676  mov     qword ptr [rbp+80h+var_108+8], r13
0x14002967a  mov     word ptr [rsp+180h+var_108], r14w
0x140029680  cmp     r14w, 4
0x140029685  jb      loc_140029A3D
0x14002968b  cmp     word ptr [r13+0], 5Ch ; '\'
  ... truncated ...
```
