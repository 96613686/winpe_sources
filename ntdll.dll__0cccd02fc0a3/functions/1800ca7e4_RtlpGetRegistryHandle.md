# RtlpGetRegistryHandle

- ea: `0x1800ca7e4`
- end: `0x1800ca976`
- name: `RtlpGetRegistryHandle`
- size: `402`
- prototype: ``
- caller_count: `9`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800c9060`
- `0x1800c9130`
- `0x1800c966c`
- `0x1800c9760`
- `0x1800c9a04`
- `0x1800c9b90`
- `0x1800c9be0`
- `0x180121d0c`
- `0x180141870`

## callees

- `0x1800152b0`
- `0x18001d490`
- `0x180021fe0`
- `0x18002ad90`
- `0x18005a9f0`
- `0x1800ca7e4`
- `0x18015e510`
- `0x18015e670`

## pseudocode

```c
__int64 __fastcall RtlpGetRegistryHandle(int a1, __int64 a2, char a3, _QWORD *a4)
{
  __int64 result; // rax
  __int64 v8; // rbx
  int appended; // ebx
  int Key; // eax
  __int128 v11; // [rsp+40h] [rbp-29h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v13[96]; // [rsp+60h] [rbp-9h] BYREF

  result = 0;
  memset(v13, 0, 44);
  v11 = 0;
  UnicodeString = 0;
  if ( (a1 & 0x40000000) != 0 )
  {
    *a4 = a2;
  }
  else
  {
    v8 = (unsigned int)a1;
    LODWORD(v8) = a1 & 0x7FFFFFFF;
    if ( a1 >= 0 )
      v8 = (unsigned int)a1;
    if ( (unsigned int)v8 >= 6 )
    {
      return 3221225485LL;
    }
    else
    {
      *((_QWORD *)&v11 + 1) = RtlpAllocateAtom(524);
      if ( *((_QWORD *)&v11 + 1) )
      {
        LODWORD(v11) = 34340864;
        if ( !(_DWORD)v8 )
          goto LABEL_7;
        if ( (_DWORD)v8 == 5 && (int)RtlFormatCurrentUserKeyPath(&UnicodeString) >= 0 )
        {
          appended = RtlAppendUnicodeStringToString(&v11, &UnicodeString);
          if ( UnicodeString.Buffer )
            RtlpSysVolFree(UnicodeString.Buffer);
        }
        else
        {
          appended = RtlAppendUnicodeToString(&v11, RtlpRegistryPaths[v8]);
        }
        if ( appended >= 0 )
        {
          appended = RtlAppendUnicodeToString(&v11, L"\\");
          if ( appended >= 0 )
          {
LABEL_7:
            appended = RtlAppendUnicodeToString(&v11, a2);
            if ( appended >= 0 )
            {
              *(_DWORD *)v13 = 48;
              *(_QWORD *)&v13[16] = &v11;
              *(_QWORD *)&v13[8] = 0;
              *(_DWORD *)&v13[24] = 576;
              *(_OWORD *)&v13[32] = 0;
              if ( a3 )
                Key = ZwCreateKey(a4, 0x40000000, v13, 0, 0, 0, 0);
              else
                Key = NtOpenKey();
              appended = Key;
            }
          }
        }
        RtlpSysVolFree(*((_QWORD *)&v11 + 1));
        return (unsigned int)appended;
      }
      else
      {
        return 3221225495LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ca7e4  push    rbp
0x1800ca7e6  push    rbx
0x1800ca7e7  push    rsi
0x1800ca7e8  push    rdi
0x1800ca7e9  push    r12
0x1800ca7eb  push    r14
0x1800ca7ed  lea     rbp, [rsp-2Fh]
0x1800ca7f2  sub     rsp, 98h
0x1800ca7f9  xorps   xmm0, xmm0
0x1800ca7fc  xor     eax, eax
0x1800ca7fe  xorps   xmm1, xmm1
0x1800ca801  mov     rdi, r9
0x1800ca804  mov     r14b, r8b
0x1800ca807  mov     rsi, rdx
0x1800ca80a  movups  [rbp+57h+var_50], xmm0
0x1800ca80e  movups  [rbp+57h+var_50+0Ch], xmm0
0x1800ca812  movups  [rbp+57h+var_60], xmm0
0x1800ca816  movups  [rbp+57h+var_80], xmm0
0x1800ca81a  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm1
0x1800ca81e  bt      ecx, 1Eh
0x1800ca822  jb      loc_1800CA908
0x1800ca828  mov     ebx, ecx
0x1800ca82a  btr     ebx, 1Fh
0x1800ca82e  test    ecx, ecx
0x1800ca830  cmovns  ebx, ecx
0x1800ca833  cmp     ebx, 6
0x1800ca836  jnb     loc_1800CA940
0x1800ca83c  mov     ecx, 20Ch
0x1800ca841  call    RtlpAllocateAtom
0x1800ca846  mov     qword ptr [rbp+57h+var_80+8], rax
0x1800ca84a  test    rax, rax
0x1800ca84d  jz      loc_1800CA90D
0x1800ca853  mov     dword ptr [rbp+57h+var_80], 20C0000h
0x1800ca85a  test    ebx, ebx
0x1800ca85c  jnz     short loc_1800CA8CE
0x1800ca85e  mov     rdx, rsi
0x1800ca861  lea     rcx, [rbp+57h+var_80]
0x1800ca865  call    RtlAppendUnicodeToString
0x1800ca86a  mov     ebx, eax
0x1800ca86c  test    eax, eax
0x1800ca86e  js      short loc_1800CA8B2
0x1800ca870  mov     dword ptr [rbp+57h+var_60], 30h ; '0'
0x1800ca877  lea     rax, [rbp+57h+var_80]
0x1800ca87b  mov     qword ptr [rbp+57h+var_50], rax
0x1800ca87f  xorps   xmm0, xmm0
0x1800ca882  mov     qword ptr [rbp+57h+var_60+8], 0
0x1800ca88a  lea     r8, [rbp+57h+var_60]
0x1800ca88e  mov     dword ptr [rbp+57h+var_50+8], 240h
0x1800ca895  mov     rcx, rdi
0x1800ca898  movdqu  [rbp+57h+var_40], xmm0
0x1800ca89d  test    r14b, r14b
0x1800ca8a0  jnz     loc_1800CA94A
0x1800ca8a6  mov     edx, 82000000h
0x1800ca8ab  call    NtOpenKey
0x1800ca8b0  mov     ebx, eax
0x1800ca8b2  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x1800ca8b6  call    RtlpSysVolFree
0x1800ca8bb  mov     eax, ebx
0x1800ca8bd  add     rsp, 98h
0x1800ca8c4  pop     r14
0x1800ca8c6  pop     r12
0x1800ca8c8  pop     rdi
0x1800ca8c9  pop     rsi
0x1800ca8ca  pop     rbx
0x1800ca8cb  pop     rbp
0x1800ca8cc  retn
0x1800ca8ce  cmp     ebx, 5
0x1800ca8d1  jz      short loc_1800CA914
0x1800ca8d3  lea     rax, RtlpRegistryPaths
0x1800ca8da  mov     rdx, [rax+rbx*8]
0x1800ca8de  lea     rcx, [rbp+57h+var_80]
0x1800ca8e2  call    RtlAppendUnicodeToString
0x1800ca8e7  mov     ebx, eax
0x1800ca8e9  test    ebx, ebx
0x1800ca8eb  js      short loc_1800CA8B2
0x1800ca8ed  lea     rdx, asc_180177BA4; "\\"
0x1800ca8f4  lea     rcx, [rbp+57h+var_80]
0x1800ca8f8  call    RtlAppendUnicodeToString
0x1800ca8fd  mov     ebx, eax
0x1800ca8ff  test    eax, eax
0x1800ca901  js      short loc_1800CA8B2
0x1800ca903  jmp     loc_1800CA85E
0x1800ca908  mov     [r9], rsi
0x1800ca90b  jmp     short loc_1800CA8BD
0x1800ca90d  mov     eax, 0C0000017h
0x1800ca912  jmp     short loc_1800CA8BD
0x1800ca914  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x1800ca918  call    RtlFormatCurrentUserKeyPath
0x1800ca91d  test    eax, eax
0x1800ca91f  js      short loc_1800CA8D3
0x1800ca921  lea     rdx, [rbp+57h+UnicodeString]
0x1800ca925  lea     rcx, [rbp+57h+var_80]
0x1800ca929  call    RtlAppendUnicodeStringToString
0x1800ca92e  mov     rcx, [rbp+57h+UnicodeString.Buffer]
0x1800ca932  mov     ebx, eax
0x1800ca934  test    rcx, rcx
0x1800ca937  jz      short loc_1800CA8E9
0x1800ca939  call    RtlpSysVolFree
0x1800ca93e  jmp     short loc_1800CA8E9
0x1800ca940  mov     eax, 0C000000Dh
0x1800ca945  jmp     loc_1800CA8BD
0x1800ca94a  mov     [rsp+0C0h+var_90], 0
0x1800ca953  xor     r9d, r9d
0x1800ca956  mov     [rsp+0C0h+var_98], 0
0x1800ca95e  mov     edx, 40000000h
0x1800ca963  mov     [rsp+0C0h+var_A0], 0
0x1800ca96c  call    ZwCreateKey
0x1800ca971  jmp     loc_1800CA8B0
```
