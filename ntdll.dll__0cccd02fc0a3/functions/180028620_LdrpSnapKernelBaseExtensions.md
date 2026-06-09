# LdrpSnapKernelBaseExtensions

- ea: `0x180028620`
- end: `0x180028b8f`
- name: `LdrpSnapKernelBaseExtensions`
- size: `1391`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002631c`

## callees

- `0x18001d490`
- `0x18001f154`
- `0x18001f900`
- `0x180021c80`
- `0x180021fe0`
- `0x180022170`
- `0x180028620`
- `0x180028ba0`
- `0x180029590`
- `0x180029b70`
- `0x18002a310`
- `0x18002a5c0`
- `0x18004cef8`
- `0x1800526f0`
- `0x180066020`
- `0x180127710`
- `0x180164360`

## pseudocode

```c
__int64 LdrpSnapKernelBaseExtensions()
{
  __int64 v0; // rbx
  __int64 result; // rax
  __int64 v2; // r12
  int Descriptor; // edi
  unsigned int v4; // r14d
  _DWORD *ApiSetMap; // r15
  unsigned int v6; // eax
  wchar_t *Buffer; // rsi
  __int64 v8; // rax
  char *v9; // rbx
  size_t v10; // rax
  unsigned int v11; // edx
  int v12; // ecx
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  int v22; // ecx
  int v23; // eax
  __int64 Length; // rcx
  char v25; // bl
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rcx
  int v30; // eax
  unsigned __int64 v31; // rax
  __int64 v32; // rax
  _WORD *v33; // rax
  __int64 v34; // rax
  char *v35; // rcx
  char *v36; // rcx
  signed __int32 v37[8]; // [rsp+0h] [rbp-59h] BYREF
  __int64 v38; // [rsp+20h] [rbp-39h]
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  __int128 v40; // [rsp+50h] [rbp-9h] BYREF
  STRING SourceString; // [rsp+60h] [rbp+7h] BYREF
  char v42; // [rsp+C0h] [rbp+67h] BYREF
  unsigned int v43; // [rsp+C8h] [rbp+6Fh] BYREF
  unsigned int v44; // [rsp+D0h] [rbp+77h]
  __int64 v45; // [rsp+D8h] [rbp+7Fh] BYREF

  v45 = 0;
  SourceString = 0;
  v43 = 0;
  v40 = 0;
  v42 = 0;
  LdrGetDllHandleByName(LdrpKernelbaseDllName, 0, &v45);
  v0 = v45;
  result = RtlImageDirectoryEntryToData(v45, 1, 0xDu, &v43);
  v2 = result;
  if ( !result )
    return result;
  Descriptor = 0;
  v4 = 0;
  ApiSetMap = NtCurrentPeb()->ApiSetMap;
  v6 = v43 >> 5;
  DestinationString = 0;
  Buffer = 0;
  v44 = v43 >> 5;
  while ( v4 < v6 )
  {
    v8 = *(unsigned int *)(v2 + 32LL * v4 + 4);
    if ( !(_DWORD)v8 )
      break;
    v9 = (char *)(v8 + v0);
    if ( !strnicmp(v9, "EXT-", 4u) )
    {
      Descriptor = 0;
      SourceString.Buffer = v9;
      *(_QWORD *)&SourceString.Length = 0;
      LOWORD(v10) = 0;
      if ( v9 )
      {
        v10 = strlen(v9);
        if ( v10 >= 0xFFFF )
          LOWORD(v10) = -2;
        SourceString.Length = v10;
        SourceString.MaximumLength = v10 + 1;
      }
      v43 = 0;
      if ( (unsigned __int8)RtlpIsUtf8Process((unsigned __int16)v10) )
      {
        if ( v12 )
        {
          RtlUTF8ToUnicodeN(0, v11, (unsigned int)&v43, (_DWORD)v9, v12);
          v11 = v43;
        }
      }
      else
      {
        _InterlockedOr(v37, v11);
        if ( word_1801C4F9C == (_WORD)v11 )
        {
          v11 = 2 * v12;
        }
        else
        {
          while ( v12 )
          {
            v32 = (unsigned __int8)*v9;
            --v12;
            ++v9;
            if ( *(_WORD *)(qword_1801C5020 + 2 * v32) )
            {
              if ( !v12 )
              {
                v11 += 2;
                break;
              }
              --v12;
              ++v9;
            }
            v11 += 2;
          }
        }
      }
      v13 = v11 + 2;
      if ( v11 + 2 > DestinationString.MaximumLength )
      {
        if ( v13 >= 0xFFFE )
        {
          Descriptor = -1073741675;
          break;
        }
        if ( Buffer )
        {
          RtlpSysVolFree(Buffer);
          *(_QWORD *)&DestinationString.Length = 0;
        }
        DestinationString.Buffer = (wchar_t *)RtlpAllocateAtom(v13);
        Buffer = DestinationString.Buffer;
        if ( !DestinationString.Buffer )
        {
          Descriptor = -1073741670;
          break;
        }
        DestinationString.MaximumLength = v13;
      }
      else
      {
        DestinationString.Length = 0;
      }
      RtlAnsiStringToUnicodeString(&DestinationString, &SourceString, 0);
      if ( (unsigned int)RtlGetCurrentServiceSessionId(v15, v14, v16, v17) )
        v21 = (__int64)NtCurrentPeb()->SharedData + 554;
      else
        v21 = 2147353476;
      if ( *(_BYTE *)v21 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
      {
        v35 = (unsigned int)RtlGetCurrentServiceSessionId(v21, v18, v19, v20)
            ? (char *)NtCurrentPeb()->SharedData + 555
            : (char *)2147353477;
        if ( (*v35 & 0x20) != 0 )
          LdrpLogEtwEvent(5328, 0, 0, 0, (__int64)&DestinationString, 0);
      }
      if ( *(_BYTE *)ApiSetMap == 7 )
      {
        v22 = (int)ApiSetMap;
      }
      else if ( *ApiSetMap != 6
             || ApiSetMap[4] <= 8u
             || (v22 = (_DWORD)ApiSetMap + 28, *((_BYTE *)ApiSetMap + 28) != 7)
             || (*((_BYTE *)ApiSetMap + 30) & 4) != 0 )
      {
        Length = DestinationString.Length;
        v25 = 0;
        Buffer = DestinationString.Buffer;
        v40 = 0;
        if ( DestinationString.Length >= 8u )
        {
          v31 = *(_QWORD *)DestinationString.Buffer & 0xFFFFFFDFFFDFFFDFuLL;
          v18 = 0x2D004900500041LL;
          if ( v31 == 0x2D004900500041LL || (v18 = 0x2D005400580045LL, v31 == 0x2D005400580045LL) )
          {
            v19 = DestinationString.Length;
            v33 = (wchar_t *)((char *)DestinationString.Buffer + DestinationString.Length);
            do
            {
              if ( (unsigned int)v19 <= 1 )
                break;
              --v33;
              v19 = (unsigned int)(v19 - 2);
            }
            while ( *v33 != 45 );
            LOWORD(v19) = (unsigned __int16)v19 >> 1;
            if ( (_WORD)v19 )
            {
              v34 = ApiSetpSearchForApiSet(ApiSetMap);
              if ( v34 )
              {
                if ( *(_DWORD *)(v34 + 20) )
                {
                  Length = *(unsigned int *)(v34 + 16);
                  v25 = 1;
                  *((_QWORD *)&v40 + 1) = (char *)ApiSetMap + *(unsigned int *)((char *)ApiSetMap + Length + 12);
                  WORD1(v40) = *(_WORD *)((char *)ApiSetMap + Length + 16);
                  LOWORD(v40) = WORD1(v40);
                }
              }
            }
          }
        }
        v42 = v25;
        goto LABEL_39;
      }
      Buffer = DestinationString.Buffer;
      LOBYTE(v20) = 1;
      v23 = ApiSetpResolveHost(
              v22,
              DestinationString.Buffer,
              DestinationString.Length >> 1,
              v20,
              0,
              (__int64)&v42,
              (__int64)&v40);
      v25 = v42;
      Descriptor = v23;
      if ( v23 < 0 )
        goto LABEL_25;
LABEL_39:
      if ( !v25 )
      {
LABEL_25:
        if ( (unsigned int)RtlGetCurrentServiceSessionId(Length, v18, v19, v20) )
          v29 = (__int64)NtCurrentPeb()->SharedData + 554;
        else
          v29 = 2147353476;
        if ( *(_BYTE *)v29 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
        {
          v36 = (unsigned int)RtlGetCurrentServiceSessionId(v29, v26, v27, v28)
              ? (char *)NtCurrentPeb()->SharedData + 555
              : (char *)2147353477;
          if ( (*v36 & 0x20) != 0 )
          {
            LdrpLogEtwEvent(5331, 0, 0, 0, (__int64)&DestinationString, 0);
            goto LABEL_42;
          }
        }
        goto LABEL_29;
      }
      if ( (_WORD)v40 )
      {
        LdrpLogDllState(0, &DestinationString, 5329);
LABEL_42:
        Buffer = DestinationString.Buffer;
        goto LABEL_29;
      }
      LdrpLogDllState(0, &DestinationString, 5330);
      Buffer = DestinationString.Buffer;
LABEL_29:
      if ( !v25 )
        goto LABEL_33;
      LOBYTE(v38) = 1;
      v30 = RtlCompareUnicodeStrings(
              L"KERNEL32.DLL",
              12,
              *((_QWORD *)&v40 + 1),
              (unsigned __int64)(unsigned __int16)v40 >> 1,
              v38);
      v0 = v45;
      if ( v30 )
        goto LABEL_34;
      Descriptor = LdrpResolveDelayLoadDescriptor(v45);
      if ( Descriptor < 0 )
        break;
      v6 = v44;
      Descriptor = 0;
      ++v4;
    }
    else
    {
LABEL_33:
      v0 = v45;
LABEL_34:
      v6 = v44;
      ++v4;
    }
  }
  if ( Buffer )
    RtlpSysVolFree(Buffer);
  return (unsigned int)Descriptor;
}

```

## disassembly

```asm
0x180028620  push    rbp
0x180028622  push    rbx
0x180028623  push    rsi
0x180028624  push    r12
0x180028626  lea     rbp, [rsp-3Fh]
0x18002862b  sub     rsp, 98h
0x180028632  xorps   xmm0, xmm0
0x180028635  lea     r8, [rbp+57h+arg_18]
0x180028639  xor     esi, esi
0x18002863b  lea     rcx, LdrpKernelbaseDllName
0x180028642  xor     edx, edx
0x180028644  mov     [rbp+57h+arg_18], rsi
0x180028648  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x18002864c  mov     [rbp+57h+arg_8], esi
0x18002864f  movups  [rbp+57h+var_60], xmm0
0x180028653  mov     [rbp+57h+arg_0], sil
0x180028657  call    LdrGetDllHandleByName
0x18002865c  mov     rbx, [rbp+57h+arg_18]
0x180028660  lea     r9, [rbp+57h+arg_8]
0x180028664  mov     rcx, rbx
0x180028667  mov     r8d, 0Dh
0x18002866d  mov     dl, 1
0x18002866f  call    RtlImageDirectoryEntryToData
0x180028674  mov     r12, rax
0x180028677  test    rax, rax
0x18002867a  jz      loc_180028A44
0x180028680  mov     rax, gs:60h
0x180028689  xorps   xmm0, xmm0
0x18002868c  mov     [rsp+0B0h+var_20], rdi
0x180028694  mov     edi, esi
0x180028696  mov     [rsp+0B0h+var_30], r14
0x18002869e  mov     r14d, esi
0x1800286a1  mov     [rsp+0B0h+var_38], r15
0x1800286a6  mov     r15, [rax+68h]
0x1800286aa  mov     eax, [rbp+57h+arg_8]
0x1800286ad  shr     eax, 5
0x1800286b0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800286b4  mov     rsi, [rbp+57h+DestinationString.Buffer]
0x1800286b8  mov     [rbp+57h+arg_10], eax
0x1800286bb  mov     [rsp+0B0h+var_28], r13
0x1800286c3  cmp     r14d, eax
0x1800286c6  jnb     loc_1800289FB
0x1800286cc  mov     r13d, r14d
0x1800286cf  shl     r13, 5
0x1800286d3  add     r13, r12
0x1800286d6  mov     eax, [r13+4]
0x1800286da  test    eax, eax
0x1800286dc  jz      loc_1800289FB
0x1800286e2  add     rbx, rax
0x1800286e5  lea     rdx, String2; "EXT-"
0x1800286ec  mov     rcx, rbx; String1
0x1800286ef  mov     r8d, 4; MaxCount
0x1800286f5  call    _strnicmp
0x1800286fa  test    eax, eax
0x1800286fc  jnz     loc_1800288A1
0x180028702  xor     edi, edi
0x180028704  mov     [rbp+57h+SourceString.Buffer], rbx
0x180028708  mov     qword ptr [rbp+57h+SourceString.Length], rdi
0x18002870c  mov     eax, edi
0x18002870e  test    rbx, rbx
0x180028711  jz      short loc_180028735
0x180028713  mov     rcx, rbx; Str
0x180028716  call    strlen
0x18002871b  mov     ecx, 0FFFEh
0x180028720  cmp     rax, 0FFFFh
0x180028726  cmovnb  rax, rcx
0x18002872a  mov     [rbp+57h+SourceString.Length], ax
0x18002872e  lea     ecx, [rax+1]
0x180028731  mov     [rbp+57h+SourceString.MaximumLength], cx
0x180028735  mov     edx, edi
0x180028737  movzx   ecx, ax
0x18002873a  mov     [rbp+57h+arg_8], edx
0x18002873d  call    RtlpIsUtf8Process
0x180028742  test    al, al
0x180028744  jnz     loc_180028A52
0x18002874a  lock or [rsp+0B0h+var_B0], edx
0x18002874e  cmp     cs:word_1801C4F9C, dx
0x180028755  jnz     loc_180028968
0x18002875b  lea     edx, [rcx+rcx]
0x18002875e  movzx   eax, [rbp+57h+DestinationString.MaximumLength]
0x180028762  lea     ebx, [rdx+2]
0x180028765  cmp     ebx, eax
0x180028767  ja      loc_18002892B
0x18002876d  mov     [rbp+57h+DestinationString.Length], di
0x180028771  xor     r8d, r8d; AllocateDestinationString
0x180028774  lea     rdx, [rbp+57h+SourceString]; SourceString
0x180028778  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002877c  call    RtlAnsiStringToUnicodeString
0x180028781  call    RtlGetCurrentServiceSessionId
0x180028786  test    eax, eax
0x180028788  jnz     loc_180028AEC
0x18002878e  mov     ecx, 7FFE0384h
0x180028793  cmp     [rcx], dil
0x180028796  jz      short loc_1800287AE
0x180028798  mov     rax, gs:60h
0x1800287a1  test    byte ptr [rax+378h], 4
0x1800287a8  jnz     loc_180028A9A
0x1800287ae  cmp     byte ptr [r15], 7
0x1800287b2  jz      loc_180028A35
0x1800287b8  cmp     dword ptr [r15], 6
0x1800287bc  jnz     loc_1800288B0
0x1800287c2  cmp     dword ptr [r15+10h], 8
0x1800287c7  jbe     loc_1800288B0
0x1800287cd  cmp     byte ptr [r15+1Ch], 7
0x1800287d2  lea     rcx, [r15+1Ch]
0x1800287d6  jnz     loc_1800288B0
0x1800287dc  test    byte ptr [r15+1Eh], 4
0x1800287e1  jnz     loc_1800288B0
0x1800287e7  movzx   r8d, [rbp+57h+DestinationString.Length]
0x1800287ec  lea     rax, [rbp+57h+var_60]
0x1800287f0  mov     rsi, [rbp+57h+DestinationString.Buffer]
0x1800287f4  mov     r9b, 1
0x1800287f7  mov     [rsp+0B0h+var_80], rax
0x1800287fc  mov     rdx, rsi
0x1800287ff  lea     rax, [rbp+57h+arg_0]
0x180028803  shr     r8w, 1
0x180028807  mov     [rsp+0B0h+var_88], rax
0x18002880c  mov     [rsp+0B0h+var_90], rdi
0x180028811  call    ApiSetpResolveHost
0x180028816  movzx   ebx, [rbp+57h+arg_0]
0x18002881a  mov     edi, eax
0x18002881c  test    eax, eax
0x18002881e  jns     loc_1800288FF
0x180028824  call    RtlGetCurrentServiceSessionId
0x180028829  test    eax, eax
0x18002882b  jnz     loc_180028B6C
0x180028831  mov     ecx, 7FFE0384h
0x180028836  cmp     byte ptr [rcx], 0
0x180028839  jz      short loc_180028851
0x18002883b  mov     rax, gs:60h
0x180028844  test    byte ptr [rax+378h], 4
0x18002884b  jnz     loc_180028B08
0x180028851  test    bl, bl
0x180028853  jz      short loc_1800288A1
0x180028855  movzx   r9d, word ptr [rbp+57h+var_60]
0x18002885a  mov     edx, 0Ch
0x18002885f  mov     r8, qword ptr [rbp+57h+var_60+8]
0x180028863  mov     rcx, cs:off_180170338; "KERNEL32.DLL"
0x18002886a  shr     r9, 1
0x18002886d  mov     byte ptr [rsp+0B0h+var_90], 1
0x180028872  call    RtlCompareUnicodeStrings
0x180028877  mov     rbx, [rbp+57h+arg_18]
0x18002887b  test    eax, eax
0x18002887d  jnz     short loc_1800288A5
0x18002887f  mov     rdx, r13
0x180028882  mov     rcx, rbx
0x180028885  call    LdrpResolveDelayLoadDescriptor
0x18002888a  mov     edi, eax
0x18002888c  test    eax, eax
0x18002888e  js      loc_1800289FB
0x180028894  mov     eax, [rbp+57h+arg_10]
0x180028897  xor     edi, edi
0x180028899  inc     r14d
0x18002889c  jmp     loc_1800286C3
0x1800288a1  mov     rbx, [rbp+57h+arg_18]
0x1800288a5  mov     eax, [rbp+57h+arg_10]
0x1800288a8  inc     r14d
0x1800288ab  jmp     loc_1800286C3
0x1800288b0  movzx   ecx, [rbp+57h+DestinationString.Length]
0x1800288b4  xor     bl, bl
0x1800288b6  mov     rsi, [rbp+57h+DestinationString.Buffer]
0x1800288ba  xorps   xmm0, xmm0
0x1800288bd  movups  [rbp+57h+var_60], xmm0
0x1800288c1  cmp     ecx, 8
0x1800288c4  jb      short loc_1800288FC
0x1800288c6  mov     rax, [rsi]
0x1800288c9  mov     rdx, 0FFFFFFDFFFDFFFDFh
0x1800288d3  and     rax, rdx
0x1800288d6  mov     rdx, 2D004900500041h
0x1800288e0  cmp     rax, rdx
0x1800288e3  jz      loc_180028990
0x1800288e9  mov     rdx, 2D005400580045h
0x1800288f3  cmp     rax, rdx
0x1800288f6  jz      loc_180028990
0x1800288fc  mov     [rbp+57h+arg_0], bl
0x1800288ff  test    bl, bl
0x180028901  jz      loc_180028824
0x180028907  xor     ecx, ecx
0x180028909  lea     rdx, [rbp+57h+DestinationString]
0x18002890d  cmp     word ptr [rbp+57h+var_60], cx
0x180028911  jz      loc_180028A86
0x180028917  mov     r8d, 14D1h
0x18002891d  call    LdrpLogDllState
0x180028922  mov     rsi, [rbp+57h+DestinationString.Buffer]
0x180028926  jmp     loc_180028851
0x18002892b  cmp     ebx, 0FFFEh
0x180028931  jnb     loc_180028A3D
0x180028937  test    rsi, rsi
0x18002893a  jz      short loc_180028948
0x18002893c  mov     rcx, rsi
0x18002893f  call    RtlpSysVolFree
0x180028944  mov     qword ptr [rbp+57h+DestinationString.Length], rdi
0x180028948  mov     ecx, ebx
0x18002894a  call    RtlpAllocateAtom
0x18002894f  mov     [rbp+57h+DestinationString.Buffer], rax
0x180028953  mov     rsi, rax
0x180028956  test    rax, rax
0x180028959  jz      loc_1800289F6
0x18002895f  mov     [rbp+57h+DestinationString.MaximumLength], bx
0x180028963  jmp     loc_180028771
0x180028968  mov     r8, cs:qword_1801C5020
0x18002896f  nop
0x180028970  test    ecx, ecx
0x180028972  jz      loc_18002875E
0x180028978  movzx   eax, byte ptr [rbx]
0x18002897b  dec     ecx
0x18002897d  inc     rbx
0x180028980  cmp     [r8+rax*2], di
0x180028985  jnz     loc_180028A74
0x18002898b  add     edx, 2
0x18002898e  jmp     short loc_180028970
0x180028990  mov     r8, rcx
0x180028993  lea     rax, [rsi+rcx]
0x180028997  cmp     r8d, 1
0x18002899b  jbe     short loc_1800289AB
0x18002899d  sub     rax, 2
0x1800289a1  add     r8d, 0FFFFFFFEh
0x1800289a5  cmp     word ptr [rax], 2Dh ; '-'
0x1800289a9  jnz     short loc_180028997
0x1800289ab  shr     r8w, 1
0x1800289af  jz      loc_1800288FC
0x1800289b5  mov     rdx, rsi
0x1800289b8  mov     rcx, r15
0x1800289bb  call    ApiSetpSearchForApiSet
0x1800289c0  test    rax, rax
0x1800289c3  jz      loc_1800288FC
0x1800289c9  cmp     [rax+14h], edi
0x1800289cc  jbe     loc_1800288FC
0x1800289d2  mov     ecx, [rax+10h]
0x1800289d5  mov     bl, 1
0x1800289d7  mov     eax, [rcx+r15+0Ch]
0x1800289dc  add     rax, r15
0x1800289df  mov     qword ptr [rbp+57h+var_60+8], rax
0x1800289e3  movzx   eax, word ptr [rcx+r15+10h]
0x1800289e9  mov     word ptr [rbp+57h+var_60+2], ax
0x1800289ed  mov     word ptr [rbp+57h+var_60], ax
0x1800289f1  jmp     loc_1800288FC
0x1800289f6  mov     edi, 0C000009Ah
0x1800289fb  mov     r15, [rsp+0B0h+var_38]
0x180028a00  mov     r14, [rsp+0B0h+var_30]
0x180028a08  mov     r13, [rsp+0B0h+var_28]
0x180028a10  test    rsi, rsi
0x180028a13  jz      short loc_180028A1D
0x180028a15  mov     rcx, rsi
0x180028a18  call    RtlpSysVolFree
0x180028a1d  mov     eax, edi
0x180028a1f  mov     rdi, [rsp+0B0h+var_20]
0x180028a27  add     rsp, 98h
0x180028a2e  pop     r12
0x180028a30  pop     rsi
0x180028a31  pop     rbx
0x180028a32  pop     rbp
0x180028a33  retn
0x180028a35  mov     rcx, r15
0x180028a38  jmp     loc_1800287E7
0x180028a3d  mov     edi, 0C0000095h
0x180028a42  jmp     short loc_1800289FB
0x180028a44  add     rsp, 98h
0x180028a4b  pop     r12
0x180028a4d  pop     rsi
0x180028a4e  pop     rbx
0x180028a4f  pop     rbp
0x180028a50  retn
0x180028a52  test    ecx, ecx
0x180028a54  jz      loc_18002875E
0x180028a5a  mov     dword ptr [rsp+0B0h+var_90], ecx
0x180028a5e  lea     r8, [rbp+57h+arg_8]
0x180028a62  xor     ecx, ecx
0x180028a64  mov     r9, rbx
0x180028a67  call    RtlUTF8ToUnicodeN
0x180028a6c  mov     edx, [rbp+57h+arg_8]
0x180028a6f  jmp     loc_18002875E
0x180028a74  test    ecx, ecx
0x180028a76  jz      loc_180028B5A
0x180028a7c  dec     ecx
0x180028a7e  inc     rbx
0x180028a81  jmp     loc_18002898B
0x180028a86  mov     r8d, 14D2h
0x180028a8c  call    LdrpLogDllState
0x180028a91  mov     rsi, [rbp+57h+DestinationString.Buffer]
0x180028a95  jmp     loc_180028851
0x180028a9a  call    RtlGetCurrentServiceSessionId
0x180028a9f  test    eax, eax
0x180028aa1  jz      loc_180028B62
0x180028aa7  mov     rax, gs:60h
0x180028ab0  mov     rcx, [rax+90h]
0x180028ab7  add     rcx, 22Bh
0x180028abe  test    byte ptr [rcx], 20h
0x180028ac1  jz      loc_1800287AE
0x180028ac7  lea     rax, [rbp+57h+DestinationString]
0x180028acb  mov     [rsp+0B0h+var_88], rdi
0x180028ad0  mov     ecx, 14D0h
0x180028ad5  mov     [rsp+0B0h+var_90], rax
0x180028ada  xor     r9d, r9d
0x180028add  xor     r8d, r8d
0x180028ae0  xor     edx, edx
0x180028ae2  call    LdrpLogEtwEvent
0x180028ae7  jmp     loc_1800287AE
0x180028aec  mov     rax, gs:60h
0x180028af5  mov     rcx, [rax+90h]
  ... truncated ...
```
