# LdrpSnapKernelBaseExtensions

- ea: `0x180028510`
- end: `0x180028a7f`
- name: `LdrpSnapKernelBaseExtensions`
- size: `1391`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002630c`

## callees

- `0x18001d490`
- `0x18001f154`
- `0x18001f8f0`
- `0x180021c70`
- `0x180021fd0`
- `0x180022160`
- `0x180028510`
- `0x180028a90`
- `0x180029480`
- `0x180029a60`
- `0x18002a200`
- `0x18002a4b0`
- `0x180069af8`
- `0x18006f0d0`
- `0x180082a00`
- `0x180128200`
- `0x180164b60`

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
0x180028510  push    rbp
0x180028512  push    rbx
0x180028513  push    rsi
0x180028514  push    r12
0x180028516  lea     rbp, [rsp-3Fh]
0x18002851b  sub     rsp, 98h
0x180028522  xorps   xmm0, xmm0
0x180028525  lea     r8, [rbp+57h+arg_18]
0x180028529  xor     esi, esi
0x18002852b  lea     rcx, LdrpKernelbaseDllName
0x180028532  xor     edx, edx
0x180028534  mov     [rbp+57h+arg_18], rsi
0x180028538  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x18002853c  mov     [rbp+57h+arg_8], esi
0x18002853f  movups  [rbp+57h+var_60], xmm0
0x180028543  mov     [rbp+57h+arg_0], sil
0x180028547  call    LdrGetDllHandleByName
0x18002854c  mov     rbx, [rbp+57h+arg_18]
0x180028550  lea     r9, [rbp+57h+arg_8]
0x180028554  mov     rcx, rbx
0x180028557  mov     r8d, 0Dh
0x18002855d  mov     dl, 1
0x18002855f  call    RtlImageDirectoryEntryToData
0x180028564  mov     r12, rax
0x180028567  test    rax, rax
0x18002856a  jz      loc_180028934
0x180028570  mov     rax, gs:60h
0x180028579  xorps   xmm0, xmm0
0x18002857c  mov     [rsp+0B0h+var_20], rdi
0x180028584  mov     edi, esi
0x180028586  mov     [rsp+0B0h+var_30], r14
0x18002858e  mov     r14d, esi
0x180028591  mov     [rsp+0B0h+var_38], r15
0x180028596  mov     r15, [rax+68h]
0x18002859a  mov     eax, [rbp+57h+arg_8]
0x18002859d  shr     eax, 5
0x1800285a0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800285a4  mov     rsi, [rbp+57h+DestinationString.Buffer]
0x1800285a8  mov     [rbp+57h+arg_10], eax
0x1800285ab  mov     [rsp+0B0h+var_28], r13
0x1800285b3  cmp     r14d, eax
0x1800285b6  jnb     loc_1800288EB
0x1800285bc  mov     r13d, r14d
0x1800285bf  shl     r13, 5
0x1800285c3  add     r13, r12
0x1800285c6  mov     eax, [r13+4]
0x1800285ca  test    eax, eax
0x1800285cc  jz      loc_1800288EB
0x1800285d2  add     rbx, rax
0x1800285d5  lea     rdx, String2; "EXT-"
0x1800285dc  mov     rcx, rbx; String1
0x1800285df  mov     r8d, 4; MaxCount
0x1800285e5  call    _strnicmp
0x1800285ea  test    eax, eax
0x1800285ec  jnz     loc_180028791
0x1800285f2  xor     edi, edi
0x1800285f4  mov     [rbp+57h+SourceString.Buffer], rbx
0x1800285f8  mov     qword ptr [rbp+57h+SourceString.Length], rdi
0x1800285fc  mov     eax, edi
0x1800285fe  test    rbx, rbx
0x180028601  jz      short loc_180028625
0x180028603  mov     rcx, rbx; Str
0x180028606  call    strlen
0x18002860b  mov     ecx, 0FFFEh
0x180028610  cmp     rax, 0FFFFh
0x180028616  cmovnb  rax, rcx
0x18002861a  mov     [rbp+57h+SourceString.Length], ax
0x18002861e  lea     ecx, [rax+1]
0x180028621  mov     [rbp+57h+SourceString.MaximumLength], cx
0x180028625  mov     edx, edi
0x180028627  movzx   ecx, ax
0x18002862a  mov     [rbp+57h+arg_8], edx
0x18002862d  call    RtlpIsUtf8Process
0x180028632  test    al, al
0x180028634  jnz     loc_180028942
0x18002863a  lock or [rsp+0B0h+var_B0], edx
0x18002863e  cmp     cs:word_1801C4F9C, dx
0x180028645  jnz     loc_180028858
0x18002864b  lea     edx, [rcx+rcx]
0x18002864e  movzx   eax, [rbp+57h+DestinationString.MaximumLength]
0x180028652  lea     ebx, [rdx+2]
0x180028655  cmp     ebx, eax
0x180028657  ja      loc_18002881B
0x18002865d  mov     [rbp+57h+DestinationString.Length], di
0x180028661  xor     r8d, r8d; AllocateDestinationString
0x180028664  lea     rdx, [rbp+57h+SourceString]; SourceString
0x180028668  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002866c  call    RtlAnsiStringToUnicodeString
0x180028671  call    RtlGetCurrentServiceSessionId
0x180028676  test    eax, eax
0x180028678  jnz     loc_1800289DC
0x18002867e  mov     ecx, 7FFE0384h
0x180028683  cmp     [rcx], dil
0x180028686  jz      short loc_18002869E
0x180028688  mov     rax, gs:60h
0x180028691  test    byte ptr [rax+378h], 4
0x180028698  jnz     loc_18002898A
0x18002869e  cmp     byte ptr [r15], 7
0x1800286a2  jz      loc_180028925
0x1800286a8  cmp     dword ptr [r15], 6
0x1800286ac  jnz     loc_1800287A0
0x1800286b2  cmp     dword ptr [r15+10h], 8
0x1800286b7  jbe     loc_1800287A0
0x1800286bd  cmp     byte ptr [r15+1Ch], 7
0x1800286c2  lea     rcx, [r15+1Ch]
0x1800286c6  jnz     loc_1800287A0
0x1800286cc  test    byte ptr [r15+1Eh], 4
0x1800286d1  jnz     loc_1800287A0
0x1800286d7  movzx   r8d, [rbp+57h+DestinationString.Length]
0x1800286dc  lea     rax, [rbp+57h+var_60]
0x1800286e0  mov     rsi, [rbp+57h+DestinationString.Buffer]
0x1800286e4  mov     r9b, 1
0x1800286e7  mov     [rsp+0B0h+var_80], rax
0x1800286ec  mov     rdx, rsi
0x1800286ef  lea     rax, [rbp+57h+arg_0]
0x1800286f3  shr     r8w, 1
0x1800286f7  mov     [rsp+0B0h+var_88], rax
0x1800286fc  mov     [rsp+0B0h+var_90], rdi
0x180028701  call    ApiSetpResolveHost
0x180028706  movzx   ebx, [rbp+57h+arg_0]
0x18002870a  mov     edi, eax
0x18002870c  test    eax, eax
0x18002870e  jns     loc_1800287EF
0x180028714  call    RtlGetCurrentServiceSessionId
0x180028719  test    eax, eax
0x18002871b  jnz     loc_180028A5C
0x180028721  mov     ecx, 7FFE0384h
0x180028726  cmp     byte ptr [rcx], 0
0x180028729  jz      short loc_180028741
0x18002872b  mov     rax, gs:60h
0x180028734  test    byte ptr [rax+378h], 4
0x18002873b  jnz     loc_1800289F8
0x180028741  test    bl, bl
0x180028743  jz      short loc_180028791
0x180028745  movzx   r9d, word ptr [rbp+57h+var_60]
0x18002874a  mov     edx, 0Ch
0x18002874f  mov     r8, qword ptr [rbp+57h+var_60+8]
0x180028753  mov     rcx, cs:off_180170338; "KERNEL32.DLL"
0x18002875a  shr     r9, 1
0x18002875d  mov     byte ptr [rsp+0B0h+var_90], 1
0x180028762  call    RtlCompareUnicodeStrings
0x180028767  mov     rbx, [rbp+57h+arg_18]
0x18002876b  test    eax, eax
0x18002876d  jnz     short loc_180028795
0x18002876f  mov     rdx, r13
0x180028772  mov     rcx, rbx
0x180028775  call    LdrpResolveDelayLoadDescriptor
0x18002877a  mov     edi, eax
0x18002877c  test    eax, eax
0x18002877e  js      loc_1800288EB
0x180028784  mov     eax, [rbp+57h+arg_10]
0x180028787  xor     edi, edi
0x180028789  inc     r14d
0x18002878c  jmp     loc_1800285B3
0x180028791  mov     rbx, [rbp+57h+arg_18]
0x180028795  mov     eax, [rbp+57h+arg_10]
0x180028798  inc     r14d
0x18002879b  jmp     loc_1800285B3
0x1800287a0  movzx   ecx, [rbp+57h+DestinationString.Length]
0x1800287a4  xor     bl, bl
0x1800287a6  mov     rsi, [rbp+57h+DestinationString.Buffer]
0x1800287aa  xorps   xmm0, xmm0
0x1800287ad  movups  [rbp+57h+var_60], xmm0
0x1800287b1  cmp     ecx, 8
0x1800287b4  jb      short loc_1800287EC
0x1800287b6  mov     rax, [rsi]
0x1800287b9  mov     rdx, 0FFFFFFDFFFDFFFDFh
0x1800287c3  and     rax, rdx
0x1800287c6  mov     rdx, 2D004900500041h
0x1800287d0  cmp     rax, rdx
0x1800287d3  jz      loc_180028880
0x1800287d9  mov     rdx, 2D005400580045h
0x1800287e3  cmp     rax, rdx
0x1800287e6  jz      loc_180028880
0x1800287ec  mov     [rbp+57h+arg_0], bl
0x1800287ef  test    bl, bl
0x1800287f1  jz      loc_180028714
0x1800287f7  xor     ecx, ecx
0x1800287f9  lea     rdx, [rbp+57h+DestinationString]
0x1800287fd  cmp     word ptr [rbp+57h+var_60], cx
0x180028801  jz      loc_180028976
0x180028807  mov     r8d, 14D1h
0x18002880d  call    LdrpLogDllState
0x180028812  mov     rsi, [rbp+57h+DestinationString.Buffer]
0x180028816  jmp     loc_180028741
0x18002881b  cmp     ebx, 0FFFEh
0x180028821  jnb     loc_18002892D
0x180028827  test    rsi, rsi
0x18002882a  jz      short loc_180028838
0x18002882c  mov     rcx, rsi
0x18002882f  call    RtlpSysVolFree
0x180028834  mov     qword ptr [rbp+57h+DestinationString.Length], rdi
0x180028838  mov     ecx, ebx
0x18002883a  call    RtlpAllocateAtom
0x18002883f  mov     [rbp+57h+DestinationString.Buffer], rax
0x180028843  mov     rsi, rax
0x180028846  test    rax, rax
0x180028849  jz      loc_1800288E6
0x18002884f  mov     [rbp+57h+DestinationString.MaximumLength], bx
0x180028853  jmp     loc_180028661
0x180028858  mov     r8, cs:qword_1801C5020
0x18002885f  nop
0x180028860  test    ecx, ecx
0x180028862  jz      loc_18002864E
0x180028868  movzx   eax, byte ptr [rbx]
0x18002886b  dec     ecx
0x18002886d  inc     rbx
0x180028870  cmp     [r8+rax*2], di
0x180028875  jnz     loc_180028964
0x18002887b  add     edx, 2
0x18002887e  jmp     short loc_180028860
0x180028880  mov     r8, rcx
0x180028883  lea     rax, [rsi+rcx]
0x180028887  cmp     r8d, 1
0x18002888b  jbe     short loc_18002889B
0x18002888d  sub     rax, 2
0x180028891  add     r8d, 0FFFFFFFEh
0x180028895  cmp     word ptr [rax], 2Dh ; '-'
0x180028899  jnz     short loc_180028887
0x18002889b  shr     r8w, 1
0x18002889f  jz      loc_1800287EC
0x1800288a5  mov     rdx, rsi
0x1800288a8  mov     rcx, r15
0x1800288ab  call    ApiSetpSearchForApiSet
0x1800288b0  test    rax, rax
0x1800288b3  jz      loc_1800287EC
0x1800288b9  cmp     [rax+14h], edi
0x1800288bc  jbe     loc_1800287EC
0x1800288c2  mov     ecx, [rax+10h]
0x1800288c5  mov     bl, 1
0x1800288c7  mov     eax, [rcx+r15+0Ch]
0x1800288cc  add     rax, r15
0x1800288cf  mov     qword ptr [rbp+57h+var_60+8], rax
0x1800288d3  movzx   eax, word ptr [rcx+r15+10h]
0x1800288d9  mov     word ptr [rbp+57h+var_60+2], ax
0x1800288dd  mov     word ptr [rbp+57h+var_60], ax
0x1800288e1  jmp     loc_1800287EC
0x1800288e6  mov     edi, 0C000009Ah
0x1800288eb  mov     r15, [rsp+0B0h+var_38]
0x1800288f0  mov     r14, [rsp+0B0h+var_30]
0x1800288f8  mov     r13, [rsp+0B0h+var_28]
0x180028900  test    rsi, rsi
0x180028903  jz      short loc_18002890D
0x180028905  mov     rcx, rsi
0x180028908  call    RtlpSysVolFree
0x18002890d  mov     eax, edi
0x18002890f  mov     rdi, [rsp+0B0h+var_20]
0x180028917  add     rsp, 98h
0x18002891e  pop     r12
0x180028920  pop     rsi
0x180028921  pop     rbx
0x180028922  pop     rbp
0x180028923  retn
0x180028925  mov     rcx, r15
0x180028928  jmp     loc_1800286D7
0x18002892d  mov     edi, 0C0000095h
0x180028932  jmp     short loc_1800288EB
0x180028934  add     rsp, 98h
0x18002893b  pop     r12
0x18002893d  pop     rsi
0x18002893e  pop     rbx
0x18002893f  pop     rbp
0x180028940  retn
0x180028942  test    ecx, ecx
0x180028944  jz      loc_18002864E
0x18002894a  mov     dword ptr [rsp+0B0h+var_90], ecx
0x18002894e  lea     r8, [rbp+57h+arg_8]
0x180028952  xor     ecx, ecx
0x180028954  mov     r9, rbx
0x180028957  call    RtlUTF8ToUnicodeN
0x18002895c  mov     edx, [rbp+57h+arg_8]
0x18002895f  jmp     loc_18002864E
0x180028964  test    ecx, ecx
0x180028966  jz      loc_180028A4A
0x18002896c  dec     ecx
0x18002896e  inc     rbx
0x180028971  jmp     loc_18002887B
0x180028976  mov     r8d, 14D2h
0x18002897c  call    LdrpLogDllState
0x180028981  mov     rsi, [rbp+57h+DestinationString.Buffer]
0x180028985  jmp     loc_180028741
0x18002898a  call    RtlGetCurrentServiceSessionId
0x18002898f  test    eax, eax
0x180028991  jz      loc_180028A52
0x180028997  mov     rax, gs:60h
0x1800289a0  mov     rcx, [rax+90h]
0x1800289a7  add     rcx, 22Bh
0x1800289ae  test    byte ptr [rcx], 20h
0x1800289b1  jz      loc_18002869E
0x1800289b7  lea     rax, [rbp+57h+DestinationString]
0x1800289bb  mov     [rsp+0B0h+var_88], rdi
0x1800289c0  mov     ecx, 14D0h
0x1800289c5  mov     [rsp+0B0h+var_90], rax
0x1800289ca  xor     r9d, r9d
0x1800289cd  xor     r8d, r8d
0x1800289d0  xor     edx, edx
0x1800289d2  call    LdrpLogEtwEvent
0x1800289d7  jmp     loc_18002869E
0x1800289dc  mov     rax, gs:60h
0x1800289e5  mov     rcx, [rax+90h]
  ... truncated ...
```
