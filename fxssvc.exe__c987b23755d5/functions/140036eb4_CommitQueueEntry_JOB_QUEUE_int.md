# CommitQueueEntry(_JOB_QUEUE *,int)

- ea: `0x140036eb4`
- end: `0x140037644`
- name: `?CommitQueueEntry@@YAHPEAU_JOB_QUEUE@@H@Z`
- size: `1936`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *, int)`
- caller_count: `7`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140031b6c`
- `0x1400328e8`
- `0x14003567c`
- `0x1400362a0`
- `0x14003bc8c`
- `0x14003d704`
- `0x14003e7ac`

## callees

- `0x140002926`
- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x140004e68`
- `0x1400354bc`
- `0x140036a18`
- `0x140036c44`
- `0x140036eb4`
- `0x140037a84`
- `0x1400392b4`
- `0x14003a228`
- `0x14003dbdc`
- `0x14003eb50`
- `0x140065d14`
- `0x140065dbc`
- `0x1400670fc`
- `0x14006a3a4`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x140037185`
- `ADVAPI32!GetLengthSid` at `0x140037185`
- `ADVAPI32!IsValidSid` at `0x140036f14`
- `ADVAPI32!IsValidSid` at `0x140036f14`
- `KERNEL32!GetLastError` at `0x140037401`
- `KERNEL32!GetLastError` at `0x140037527`
- `KERNEL32!GetLastError` at `0x140037573`
- `KERNEL32!GetLastError` at `0x140037401`
- `KERNEL32!GetLastError` at `0x140037527`
- `KERNEL32!GetLastError` at `0x140037573`
- `KERNEL32!CloseHandle` at `0x140037505`
- `KERNEL32!CloseHandle` at `0x14003761a`
- `KERNEL32!CloseHandle` at `0x140037505`
- `KERNEL32!CloseHandle` at `0x14003761a`
- `KERNEL32!DeleteFileW` at `0x140037551`
- `KERNEL32!DeleteFileW` at `0x140037551`

## pseudocode

```c
__int64 __fastcall CommitQueueEntry(struct _JOB_QUEUE *a1, int a2)
{
  void *v4; // rcx
  unsigned int v5; // r15d
  char *v6; // rax
  char *v7; // r14
  _WORD *v9; // r9
  _WORD *v10; // r10
  __int64 v11; // r11
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // esi
  _WORD *v16; // rcx
  __int64 v17; // r9
  CMapDeviceId *v18; // rcx
  __int64 v19; // rdx
  _WORD *v20; // rax
  _WORD *v21; // rdx
  _WORD *v22; // rcx
  void *v23; // rcx
  DWORD LengthSid; // eax
  __int64 v25; // rbx
  CMapDeviceId *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r9
  DWORD LastError; // eax
  void *File; // rax
  __int64 v31; // rbx
  int v32; // eax
  char v33; // al
  int v34; // edx
  int v35; // r8d
  CMapDeviceId *v36; // rcx
  int v37; // edx
  unsigned __int64 v38; // [rsp+70h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  v4 = (void *)*((_QWORD *)a1 + 51);
  if ( v4 && !IsValidSid(v4) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        116,
        &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        *((unsigned int *)a1 + 8));
    }
    return 0;
  }
  v5 = CalcJobQueuePersistentSize(a1) + 1656;
  v6 = (char *)pMemAlloc(v5);
  v7 = v6;
  if ( !v6 )
    return 0;
  memset_0(v6, 0, v5);
  v9 = (_WORD *)((char *)a1 + 1176);
  v38 = 1656;
  v10 = v7 + 1136;
  *(_DWORD *)v7 = 1656;
  v11 = 2147483646;
  v12 = 256;
  *((_QWORD *)v7 + 1) = *((_QWORD *)a1 + 2);
  v13 = 2147483646;
  v14 = 256;
  *((_QWORD *)v7 + 2) = *((_QWORD *)a1 + 3);
  v15 = 1;
  *((_QWORD *)v7 + 48) = *((_QWORD *)a1 + 52);
  *((_QWORD *)v7 + 49) = *((_QWORD *)a1 + 53);
  *((_DWORD *)v7 + 6) = *((_DWORD *)a1 + 9);
  *((_DWORD *)v7 + 10) = *((_DWORD *)a1 + 461);
  *((_DWORD *)v7 + 412) = *((_DWORD *)a1 + 422);
  do
  {
    if ( !v13 )
      break;
    if ( !*v9 )
      break;
    *v10++ = *v9++;
    --v13;
    --v14;
  }
  while ( v14 );
  v16 = v10 - 1;
  v17 = v14 == 0 ? 0x8007007A : 0;
  if ( v14 )
    v16 = v10;
  *v16 = 0;
  if ( v14 )
  {
    v20 = (_WORD *)((char *)a1 + 648);
    v21 = v7 + 556;
    do
    {
      if ( !v11 )
        break;
      if ( !*v20 )
        break;
      *v21++ = *v20++;
      --v11;
      --v12;
    }
    while ( v12 );
    v22 = v21 - 1;
    v17 = v12 == 0 ? 0x8007007A : 0;
    if ( v12 )
      v22 = v21;
    *v22 = 0;
    if ( !v12 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_25;
      }
      v19 = 118;
      goto LABEL_24;
    }
    *((_DWORD *)v7 + 11) = *((_DWORD *)a1 + 16);
    *((_DWORD *)v7 + 48) = *((_DWORD *)a1 + 58);
    *((_DWORD *)v7 + 85) = *((_DWORD *)a1 + 95);
    *((_DWORD *)v7 + 84) = *((_DWORD *)a1 + 94);
    *((_DWORD *)v7 + 86) = *((_DWORD *)a1 + 97);
    if ( *((_DWORD *)a1 + 9) == 2 )
      *((_QWORD *)v7 + 68) = *(_QWORD *)(*((_QWORD *)a1 + 73) + 16LL);
    *((_DWORD *)v7 + 138) = *((_DWORD *)a1 + 148);
    *((_QWORD *)v7 + 140) = *((_QWORD *)a1 + 145);
    *((_QWORD *)v7 + 141) = *((_QWORD *)a1 + 146);
    v23 = (void *)*((_QWORD *)a1 + 51);
    if ( v23 )
    {
      LengthSid = GetLengthSid(v23);
      *((_QWORD *)v7 + 47) = 1656;
      v25 = LengthSid;
      memcpy_0(v7 + 1656, *((const void **)a1 + 51), LengthSid);
      v38 = v25 + 1656;
    }
    StoreString(*((unsigned __int16 **)a1 + 55), v5);
    *((_OWORD *)v7 + 69) = 0;
    StoreString(*((unsigned __int16 **)a1 + 7), v5);
    if ( *((_DWORD *)a1 + 9) == 32 || *((_DWORD *)a1 + 9) == 8 )
      StoreString(*((unsigned __int16 **)a1 + 9), v5);
    if ( !(unsigned int)JobParamsExSerialize(
                          (struct _JOB_QUEUE *)((char *)a1 + 80),
                          (struct _FAX_JOB_PARAM_EXW *)(v7 + 56),
                          (unsigned __int8 *)v7,
                          &v38,
                          v5) )
    {
      v15 = 122;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v27 = 119;
      goto LABEL_49;
    }
    if ( !(unsigned int)CoverPageExSerialize(
                          (struct _JOB_QUEUE *)((char *)a1 + 176),
                          (struct _FAX_COVERPAGE_INFO_EXW *)(v7 + 152),
                          (unsigned __int8 *)v7,
                          &v38,
                          v5) )
    {
      v15 = 122;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v27 = 120;
      goto LABEL_49;
    }
    if ( !(unsigned int)PersonalProfileSerialize(
                          (struct _JOB_QUEUE *)((char *)a1 + 240),
                          (struct _FAX_PERSONAL_PROFILEW *)(v7 + 200),
                          (unsigned __int8 *)v7,
                          &v38,
                          v5) )
    {
      v15 = 122;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v27 = 121;
      goto LABEL_49;
    }
    StoreString(*((unsigned __int16 **)a1 + 50), v5);
    if ( !(unsigned int)PersonalProfileSerialize(
                          (struct _JOB_QUEUE *)((char *)a1 + 448),
                          (struct _FAX_PERSONAL_PROFILEW *)(v7 + 408),
                          (unsigned __int8 *)v7,
                          &v38,
                          v5) )
    {
      v15 = 122;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v27 = 122;
LABEL_49:
      WPP_SF_d(*((_QWORD *)v26 + 2), v27, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, *((unsigned int *)a1 + 8));
      goto LABEL_105;
    }
    if ( *((_DWORD *)a1 + 9) == 8 )
    {
      v15 = SerializeRoutingInfo(a1, (struct _JOB_QUEUE_FILE *)v7, &v38, v5);
      if ( !v15 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            123,
            &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
            *((unsigned int *)a1 + 8),
            LastError);
        }
        goto LABEL_105;
      }
    }
    File = (void *)InternalSafeCreateFile(*((LPCWSTR *)a1 + 7), 0x40000000u, 0, v28, 2u, -2147483520);
    v31 = (__int64)File;
    if ( File == (void *)-1LL )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          124,
          (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          *((_DWORD *)a1 + 8),
          *((_QWORD *)a1 + 7));
      }
      v15 = 0;
      goto LABEL_105;
    }
    v32 = CommitHashedQueueEntry(File, v7, v5);
    if ( !v32 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          129,
          (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          *((_DWORD *)a1 + 8),
          *((_QWORD *)a1 + 7));
      }
      goto LABEL_104;
    }
    if ( a2 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_lSl(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          125,
          (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          *((_DWORD *)a1 + 8),
          *((_QWORD *)a1 + 7),
          v32);
      }
      if ( !CloseHandle((HANDLE)v31)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v33 = GetLastError();
        WPP_SF_SDl(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, v35, *((_QWORD *)v7 + 4), v31, v33);
      }
      v31 = -1;
      if ( !DeleteFileW(*((LPCWSTR *)a1 + 7))
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LOBYTE(v32) = GetLastError();
        v36 = WPP_GLOBAL_Control;
        v37 = 127;
LABEL_97:
        WPP_SF_lSl(
          *((_QWORD *)v36 + 2),
          v37,
          (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          *((_DWORD *)a1 + 8),
          *((_QWORD *)a1 + 7),
          v32);
      }
    }
    else
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v37 = 128;
        goto LABEL_97;
      }
    }
    v15 = 0;
    if ( v31 == -1 )
      goto LABEL_105;
LABEL_104:
    CloseHandle((HANDLE)v31);
    goto LABEL_105;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_25;
  }
  v19 = 117;
LABEL_24:
  WPP_SF_d(*((_QWORD *)v18 + 2), v19, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v17);
LABEL_25:
  v15 = 0;
LABEL_105:
  pMemFree(v7);
  return v15;
}

```

## disassembly

```asm
0x140036eb4  mov     [rsp+arg_8], rbx
0x140036eb9  mov     [rsp+arg_10], rsi
0x140036ebe  push    rdi
0x140036ebf  push    r12
0x140036ec1  push    r13
0x140036ec3  push    r14
0x140036ec5  push    r15
0x140036ec7  sub     rsp, 40h
0x140036ecb  mov     r13d, edx
0x140036ece  mov     rdi, rcx
0x140036ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x140036ed8  lea     rbx, WPP_GLOBAL_Control
0x140036edf  mov     r12b, 4
0x140036ee2  cmp     rcx, rbx
0x140036ee5  jz      short loc_140036F08
0x140036ee7  test    [rcx+1Ch], r12b
0x140036eeb  jz      short loc_140036F08
0x140036eed  cmp     byte ptr [rcx+19h], 5
0x140036ef1  jb      short loc_140036F08
0x140036ef3  mov     rcx, [rcx+10h]
0x140036ef7  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140036efe  mov     edx, 73h ; 's'
0x140036f03  call    WPP_SF_
0x140036f08  mov     rcx, [rdi+198h]; pSid
0x140036f0f  test    rcx, rcx
0x140036f12  jz      short loc_140036F4F
0x140036f14  call    cs:__imp_IsValidSid
0x140036f1a  test    eax, eax
0x140036f1c  jnz     short loc_140036F4F
0x140036f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140036f25  cmp     rcx, rbx
0x140036f28  jz      short loc_140036F71
0x140036f2a  test    [rcx+1Ch], r12b
0x140036f2e  jz      short loc_140036F71
0x140036f30  cmp     byte ptr [rcx+19h], 2
0x140036f34  jb      short loc_140036F71
0x140036f36  mov     r9d, [rdi+20h]
0x140036f3a  lea     edx, [rax+74h]
0x140036f3d  mov     rcx, [rcx+10h]
0x140036f41  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140036f48  call    WPP_SF_d
0x140036f4d  jmp     short loc_140036F71
0x140036f4f  mov     rcx, rdi; struct _JOB_QUEUE *
0x140036f52  call    ?CalcJobQueuePersistentSize@@YAKQEAU_JOB_QUEUE@@@Z; CalcJobQueuePersistentSize(_JOB_QUEUE * const)
0x140036f57  lea     r15d, [rax+678h]
0x140036f5e  mov     ecx, r15d; dwBytes
0x140036f61  mov     ebx, r15d
0x140036f64  call    pMemAlloc
0x140036f69  mov     r14, rax
0x140036f6c  test    rax, rax
0x140036f6f  jnz     short loc_140036F78
0x140036f71  xor     eax, eax
0x140036f73  jmp     loc_14003762A
0x140036f78  mov     r8, rbx; Size
0x140036f7b  xor     edx, edx; Val
0x140036f7d  mov     rcx, r14; void *
0x140036f80  call    memset_0
0x140036f85  mov     eax, 678h
0x140036f8a  lea     r9, [rdi+498h]
0x140036f91  mov     [rsp+68h+arg_0], rax
0x140036f96  lea     r10, [r14+470h]
0x140036f9d  mov     [r14], eax
0x140036fa0  mov     r11d, 7FFFFFFEh
0x140036fa6  mov     rax, [rdi+10h]
0x140036faa  mov     r8d, 100h
0x140036fb0  mov     [r14+8], rax
0x140036fb4  mov     ecx, r11d
0x140036fb7  mov     rax, [rdi+18h]
0x140036fbb  mov     edx, r8d
0x140036fbe  mov     [r14+10h], rax
0x140036fc2  mov     esi, 1
0x140036fc7  mov     rax, [rdi+1A0h]
0x140036fce  xor     ebx, ebx
0x140036fd0  mov     [r14+180h], rax
0x140036fd7  mov     rax, [rdi+1A8h]
0x140036fde  mov     [r14+188h], rax
0x140036fe5  mov     eax, [rdi+24h]
0x140036fe8  mov     [r14+18h], eax
0x140036fec  mov     eax, [rdi+734h]
0x140036ff2  mov     [r14+28h], eax
0x140036ff6  mov     eax, [rdi+698h]
0x140036ffc  mov     [r14+670h], eax
0x140037003  test    rcx, rcx
0x140037006  jz      short loc_140037025
0x140037008  movzx   eax, word ptr [r9]
0x14003700c  test    ax, ax
0x14003700f  jz      short loc_140037025
0x140037011  mov     [r10], ax
0x140037015  add     r9, 2
0x140037019  add     r10, 2
0x14003701d  sub     rcx, rsi
0x140037020  sub     rdx, rsi
0x140037023  jnz     short loc_140037003
0x140037025  mov     rax, rdx
0x140037028  lea     rcx, [r10-2]
0x14003702c  neg     rax
0x14003702f  sbb     r9d, r9d
0x140037032  not     r9d
0x140037035  and     r9d, 8007007Ah
0x14003703c  test    rdx, rdx
0x14003703f  cmovnz  rcx, r10
0x140037043  mov     [rcx], bx
0x140037046  jnz     short loc_140037083
0x140037048  mov     rcx, cs:WPP_GLOBAL_Control
0x14003704f  lea     r15, WPP_GLOBAL_Control
0x140037056  cmp     rcx, r15
0x140037059  jz      short loc_14003707C
0x14003705b  test    [rcx+1Ch], r12b
0x14003705f  jz      short loc_14003707C
0x140037061  cmp     byte ptr [rcx+19h], 2
0x140037065  jb      short loc_14003707C
0x140037067  mov     edx, 75h ; 'u'
0x14003706c  mov     rcx, [rcx+10h]
0x140037070  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140037077  call    WPP_SF_d
0x14003707c  mov     esi, ebx
0x14003707e  jmp     loc_140037620
0x140037083  lea     rax, [rdi+288h]
0x14003708a  lea     rdx, [r14+22Ch]
0x140037091  test    r11, r11
0x140037094  jz      short loc_1400370B1
0x140037096  movzx   ecx, word ptr [rax]
0x140037099  test    cx, cx
0x14003709c  jz      short loc_1400370B1
0x14003709e  mov     [rdx], cx
0x1400370a1  add     rax, 2
0x1400370a5  add     rdx, 2
0x1400370a9  sub     r11, rsi
0x1400370ac  sub     r8, rsi
0x1400370af  jnz     short loc_140037091
0x1400370b1  mov     rax, r8
0x1400370b4  lea     rcx, [rdx-2]
0x1400370b8  neg     rax
0x1400370bb  sbb     r9d, r9d
0x1400370be  not     r9d
0x1400370c1  and     r9d, 8007007Ah
0x1400370c8  test    r8, r8
0x1400370cb  cmovnz  rcx, rdx
0x1400370cf  mov     [rcx], bx
0x1400370d2  jnz     short loc_1400370FD
0x1400370d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400370db  lea     r15, WPP_GLOBAL_Control
0x1400370e2  cmp     rcx, r15
0x1400370e5  jz      short loc_14003707C
0x1400370e7  test    [rcx+1Ch], r12b
0x1400370eb  jz      short loc_14003707C
0x1400370ed  cmp     byte ptr [rcx+19h], 2
0x1400370f1  jb      short loc_14003707C
0x1400370f3  mov     edx, 76h ; 'v'
0x1400370f8  jmp     loc_14003706C
0x1400370fd  mov     eax, [rdi+40h]
0x140037100  mov     [r14+2Ch], eax
0x140037104  mov     eax, [rdi+0E8h]
0x14003710a  mov     [r14+0C0h], eax
0x140037111  mov     eax, [rdi+17Ch]
0x140037117  mov     [r14+154h], eax
0x14003711e  mov     eax, [rdi+178h]
0x140037124  mov     [r14+150h], eax
0x14003712b  mov     eax, [rdi+184h]
0x140037131  mov     [r14+158h], eax
0x140037138  cmp     dword ptr [rdi+24h], 2
0x14003713c  jnz     short loc_140037150
0x14003713e  mov     rax, [rdi+248h]
0x140037145  mov     rcx, [rax+10h]
0x140037149  mov     [r14+220h], rcx
0x140037150  mov     eax, [rdi+250h]
0x140037156  mov     [r14+228h], eax
0x14003715d  mov     rax, [rdi+488h]
0x140037164  mov     [r14+460h], rax
0x14003716b  mov     rax, [rdi+490h]
0x140037172  mov     [r14+468h], rax
0x140037179  mov     rcx, [rdi+198h]; pSid
0x140037180  test    rcx, rcx
0x140037183  jz      short loc_1400371BA
0x140037185  call    cs:__imp_GetLengthSid
0x14003718b  mov     qword ptr [r14+178h], 678h
0x140037196  lea     rcx, [r14+678h]; void *
0x14003719d  mov     rdx, [rdi+198h]; Src
0x1400371a4  mov     r8d, eax; Size
0x1400371a7  mov     ebx, eax
0x1400371a9  call    memcpy_0
0x1400371ae  lea     rax, [rbx+678h]
0x1400371b5  mov     [rsp+68h+arg_0], rax
0x1400371ba  mov     rcx, [rdi+1B8h]; unsigned __int16 *
0x1400371c1  lea     rdx, [r14+190h]
0x1400371c8  lea     r9, [rsp+68h+arg_0]
0x1400371cd  mov     [rsp+68h+var_48], r15d; int
0x1400371d2  mov     r8, r14
0x1400371d5  call    StoreString
0x1400371da  xorps   xmm0, xmm0
0x1400371dd  mov     [rsp+68h+var_48], r15d; int
0x1400371e2  movups  xmmword ptr [r14+450h], xmm0
0x1400371ea  mov     rcx, [rdi+38h]; unsigned __int16 *
0x1400371ee  lea     r9, [rsp+68h+arg_0]
0x1400371f3  mov     r8, r14
0x1400371f6  lea     rdx, [r14+20h]
0x1400371fa  call    StoreString
0x1400371ff  cmp     dword ptr [rdi+24h], 20h ; ' '
0x140037203  jz      short loc_14003720B
0x140037205  cmp     dword ptr [rdi+24h], 8
0x140037209  jnz     short loc_140037225
0x14003720b  mov     rcx, [rdi+48h]; unsigned __int16 *
0x14003720f  lea     rdx, [r14+30h]
0x140037213  lea     r9, [rsp+68h+arg_0]
0x140037218  mov     [rsp+68h+var_48], r15d; int
0x14003721d  mov     r8, r14
0x140037220  call    StoreString
0x140037225  lea     rdx, [r14+38h]; struct _FAX_JOB_PARAM_EXW *
0x140037229  mov     [rsp+68h+var_48], r15d; unsigned int
0x14003722e  lea     rcx, [rdi+50h]; struct _FAX_JOB_PARAM_EXW *
0x140037232  mov     r8, r14; unsigned __int8 *
0x140037235  lea     r9, [rsp+68h+arg_0]; unsigned __int64 *
0x14003723a  call    ?JobParamsExSerialize@@YAHPEBU_FAX_JOB_PARAM_EXW@@PEAU1@PEAEPEA_KK@Z; JobParamsExSerialize(_FAX_JOB_PARAM_EXW const *,_FAX_JOB_PARAM_EXW *,uchar *,unsigned __int64 *,ulong)
0x14003723f  test    eax, eax
0x140037241  jnz     short loc_14003728D
0x140037243  lea     esi, [rax+7Ah]
0x140037246  mov     rcx, cs:WPP_GLOBAL_Control
0x14003724d  lea     r15, WPP_GLOBAL_Control
0x140037254  cmp     rcx, r15
0x140037257  jz      loc_140037620
0x14003725d  test    [rcx+1Ch], r12b
0x140037261  jz      loc_140037620
0x140037267  cmp     byte ptr [rcx+19h], 2
0x14003726b  jb      loc_140037620
0x140037271  lea     edx, [rax+77h]
0x140037274  mov     r9d, [rdi+20h]
0x140037278  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003727f  mov     rcx, [rcx+10h]
0x140037283  call    WPP_SF_d
0x140037288  jmp     loc_140037620
0x14003728d  lea     rdx, [r14+98h]; struct _FAX_COVERPAGE_INFO_EXW *
0x140037294  mov     [rsp+68h+var_48], r15d; unsigned int
0x140037299  lea     rcx, [rdi+0B0h]; struct _FAX_COVERPAGE_INFO_EXW *
0x1400372a0  mov     r8, r14; unsigned __int8 *
0x1400372a3  lea     r9, [rsp+68h+arg_0]; unsigned __int64 *
0x1400372a8  call    ?CoverPageExSerialize@@YAHPEBU_FAX_COVERPAGE_INFO_EXW@@PEAU1@PEAEPEA_KK@Z; CoverPageExSerialize(_FAX_COVERPAGE_INFO_EXW const *,_FAX_COVERPAGE_INFO_EXW *,uchar *,unsigned __int64 *,ulong)
0x1400372ad  test    eax, eax
0x1400372af  jnz     short loc_1400372E4
0x1400372b1  lea     esi, [rax+7Ah]
0x1400372b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400372bb  lea     r15, WPP_GLOBAL_Control
0x1400372c2  cmp     rcx, r15
0x1400372c5  jz      loc_140037620
0x1400372cb  test    [rcx+1Ch], r12b
0x1400372cf  jz      loc_140037620
0x1400372d5  cmp     byte ptr [rcx+19h], 2
0x1400372d9  jb      loc_140037620
0x1400372df  lea     edx, [rax+78h]
0x1400372e2  jmp     short loc_140037274
0x1400372e4  lea     rdx, [r14+0C8h]; struct _FAX_PERSONAL_PROFILEW *
0x1400372eb  mov     [rsp+68h+var_48], r15d; unsigned int
0x1400372f0  lea     rcx, [rdi+0F0h]; struct _FAX_PERSONAL_PROFILEW *
0x1400372f7  mov     r8, r14; unsigned __int8 *
0x1400372fa  lea     r9, [rsp+68h+arg_0]; unsigned __int64 *
0x1400372ff  call    ?PersonalProfileSerialize@@YAHPEBU_FAX_PERSONAL_PROFILEW@@PEAU1@PEAEPEA_KK@Z; PersonalProfileSerialize(_FAX_PERSONAL_PROFILEW const *,_FAX_PERSONAL_PROFILEW *,uchar *,unsigned __int64 *,ulong)
0x140037304  test    eax, eax
0x140037306  jnz     short loc_14003733E
0x140037308  lea     esi, [rax+7Ah]
0x14003730b  mov     rcx, cs:WPP_GLOBAL_Control
0x140037312  lea     r15, WPP_GLOBAL_Control
0x140037319  cmp     rcx, r15
0x14003731c  jz      loc_140037620
0x140037322  test    [rcx+1Ch], r12b
0x140037326  jz      loc_140037620
0x14003732c  cmp     byte ptr [rcx+19h], 2
0x140037330  jb      loc_140037620
0x140037336  lea     edx, [rax+79h]
0x140037339  jmp     loc_140037274
0x14003733e  mov     rcx, [rdi+190h]; unsigned __int16 *
0x140037345  lea     rdx, [r14+170h]
0x14003734c  lea     r9, [rsp+68h+arg_0]
0x140037351  mov     [rsp+68h+var_48], r15d; int
0x140037356  mov     r8, r14
0x140037359  call    StoreString
0x14003735e  lea     rdx, [r14+198h]; struct _FAX_PERSONAL_PROFILEW *
0x140037365  mov     [rsp+68h+var_48], r15d; unsigned int
0x14003736a  lea     rcx, [rdi+1C0h]; struct _FAX_PERSONAL_PROFILEW *
0x140037371  mov     r8, r14; unsigned __int8 *
0x140037374  lea     r9, [rsp+68h+arg_0]; unsigned __int64 *
0x140037379  call    ?PersonalProfileSerialize@@YAHPEBU_FAX_PERSONAL_PROFILEW@@PEAU1@PEAEPEA_KK@Z; PersonalProfileSerialize(_FAX_PERSONAL_PROFILEW const *,_FAX_PERSONAL_PROFILEW *,uchar *,unsigned __int64 *,ulong)
0x14003737e  test    eax, eax
0x140037380  jnz     short loc_1400373B7
0x140037382  lea     esi, [rax+7Ah]
0x140037385  mov     rcx, cs:WPP_GLOBAL_Control
0x14003738c  lea     r15, WPP_GLOBAL_Control
0x140037393  cmp     rcx, r15
0x140037396  jz      loc_140037620
0x14003739c  test    [rcx+1Ch], r12b
0x1400373a0  jz      loc_140037620
0x1400373a6  cmp     byte ptr [rcx+19h], 2
0x1400373aa  jb      loc_140037620
0x1400373b0  mov     edx, esi
0x1400373b2  jmp     loc_140037274
0x1400373b7  cmp     dword ptr [rdi+24h], 8
0x1400373bb  jnz     short loc_14003742E
0x1400373bd  mov     r9d, r15d; unsigned int
0x1400373c0  lea     r8, [rsp+68h+arg_0]; unsigned __int64 *
0x1400373c5  mov     rdx, r14; struct _JOB_QUEUE_FILE *
0x1400373c8  mov     rcx, rdi; struct _JOB_QUEUE *
0x1400373cb  call    ?SerializeRoutingInfo@@YAHPEBU_JOB_QUEUE@@PEAU_JOB_QUEUE_FILE@@PEA_KK@Z; SerializeRoutingInfo(_JOB_QUEUE const *,_JOB_QUEUE_FILE *,unsigned __int64 *,ulong)
  ... truncated ...
```
