# RtlpGetRegistryHandle

- ea: `0x180038ed4`
- end: `0x180039066`
- name: `RtlpGetRegistryHandle`
- size: `402`
- prototype: ``
- caller_count: `9`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800380f4`
- `0x180038280`
- `0x1800382d0`
- `0x180039610`
- `0x1800396ec`
- `0x180039bf0`
- `0x18010cea0`
- `0x1801227fc`
- `0x180142200`

## callees

- `0x1800152b0`
- `0x18001d490`
- `0x180021fd0`
- `0x180036fa0`
- `0x180038ed4`
- `0x1800773d0`
- `0x18015ed20`
- `0x18015ee80`

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
0x180038ed4  push    rbp
0x180038ed6  push    rbx
0x180038ed7  push    rsi
0x180038ed8  push    rdi
0x180038ed9  push    r12
0x180038edb  push    r14
0x180038edd  lea     rbp, [rsp-2Fh]
0x180038ee2  sub     rsp, 98h
0x180038ee9  xorps   xmm0, xmm0
0x180038eec  xor     eax, eax
0x180038eee  xorps   xmm1, xmm1
0x180038ef1  mov     rdi, r9
0x180038ef4  mov     r14b, r8b
0x180038ef7  mov     rsi, rdx
0x180038efa  movups  [rbp+57h+var_50], xmm0
0x180038efe  movups  [rbp+57h+var_50+0Ch], xmm0
0x180038f02  movups  [rbp+57h+var_60], xmm0
0x180038f06  movups  [rbp+57h+var_80], xmm0
0x180038f0a  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm1
0x180038f0e  bt      ecx, 1Eh
0x180038f12  jb      loc_180038FF8
0x180038f18  mov     ebx, ecx
0x180038f1a  btr     ebx, 1Fh
0x180038f1e  test    ecx, ecx
0x180038f20  cmovns  ebx, ecx
0x180038f23  cmp     ebx, 6
0x180038f26  jnb     loc_180039030
0x180038f2c  mov     ecx, 20Ch
0x180038f31  call    RtlpAllocateAtom
0x180038f36  mov     qword ptr [rbp+57h+var_80+8], rax
0x180038f3a  test    rax, rax
0x180038f3d  jz      loc_180038FFD
0x180038f43  mov     dword ptr [rbp+57h+var_80], 20C0000h
0x180038f4a  test    ebx, ebx
0x180038f4c  jnz     short loc_180038FBE
0x180038f4e  mov     rdx, rsi
0x180038f51  lea     rcx, [rbp+57h+var_80]
0x180038f55  call    RtlAppendUnicodeToString
0x180038f5a  mov     ebx, eax
0x180038f5c  test    eax, eax
0x180038f5e  js      short loc_180038FA2
0x180038f60  mov     dword ptr [rbp+57h+var_60], 30h ; '0'
0x180038f67  lea     rax, [rbp+57h+var_80]
0x180038f6b  mov     qword ptr [rbp+57h+var_50], rax
0x180038f6f  xorps   xmm0, xmm0
0x180038f72  mov     qword ptr [rbp+57h+var_60+8], 0
0x180038f7a  lea     r8, [rbp+57h+var_60]
0x180038f7e  mov     dword ptr [rbp+57h+var_50+8], 240h
0x180038f85  mov     rcx, rdi
0x180038f88  movdqu  [rbp+57h+var_40], xmm0
0x180038f8d  test    r14b, r14b
0x180038f90  jnz     loc_18003903A
0x180038f96  mov     edx, 82000000h
0x180038f9b  call    NtOpenKey
0x180038fa0  mov     ebx, eax
0x180038fa2  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x180038fa6  call    RtlpSysVolFree
0x180038fab  mov     eax, ebx
0x180038fad  add     rsp, 98h
0x180038fb4  pop     r14
0x180038fb6  pop     r12
0x180038fb8  pop     rdi
0x180038fb9  pop     rsi
0x180038fba  pop     rbx
0x180038fbb  pop     rbp
0x180038fbc  retn
0x180038fbe  cmp     ebx, 5
0x180038fc1  jz      short loc_180039004
0x180038fc3  lea     rax, RtlpRegistryPaths
0x180038fca  mov     rdx, [rax+rbx*8]
0x180038fce  lea     rcx, [rbp+57h+var_80]
0x180038fd2  call    RtlAppendUnicodeToString
0x180038fd7  mov     ebx, eax
0x180038fd9  test    ebx, ebx
0x180038fdb  js      short loc_180038FA2
0x180038fdd  lea     rdx, asc_180178554; "\\"
0x180038fe4  lea     rcx, [rbp+57h+var_80]
0x180038fe8  call    RtlAppendUnicodeToString
0x180038fed  mov     ebx, eax
0x180038fef  test    eax, eax
0x180038ff1  js      short loc_180038FA2
0x180038ff3  jmp     loc_180038F4E
0x180038ff8  mov     [r9], rsi
0x180038ffb  jmp     short loc_180038FAD
0x180038ffd  mov     eax, 0C0000017h
0x180039002  jmp     short loc_180038FAD
0x180039004  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180039008  call    RtlFormatCurrentUserKeyPath
0x18003900d  test    eax, eax
0x18003900f  js      short loc_180038FC3
0x180039011  lea     rdx, [rbp+57h+UnicodeString]
0x180039015  lea     rcx, [rbp+57h+var_80]
0x180039019  call    RtlAppendUnicodeStringToString
0x18003901e  mov     rcx, [rbp+57h+UnicodeString.Buffer]
0x180039022  mov     ebx, eax
0x180039024  test    rcx, rcx
0x180039027  jz      short loc_180038FD9
0x180039029  call    RtlpSysVolFree
0x18003902e  jmp     short loc_180038FD9
0x180039030  mov     eax, 0C000000Dh
0x180039035  jmp     loc_180038FAD
0x18003903a  mov     [rsp+0C0h+var_90], 0
0x180039043  xor     r9d, r9d
0x180039046  mov     [rsp+0C0h+var_98], 0
0x18003904e  mov     edx, 40000000h
0x180039053  mov     [rsp+0C0h+var_A0], 0
0x18003905c  call    ZwCreateKey
0x180039061  jmp     loc_180038FA0
```
