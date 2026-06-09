# AppendCredentialHistoryMap

- ea: `0x1800284ac`
- end: `0x1800285d6`
- name: `AppendCredentialHistoryMap`
- size: `298`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800285dc`

## callees

- `0x180007f10`
- `0x18001d810`
- `0x1800284ac`
- `0x1800296c8`
- `0x180029ed4`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180028540`
- `RPCRT4!UuidCreate` at `0x180028540`

## string_xrefs

- `0x18002859e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
__int64 __fastcall AppendCredentialHistoryMap(HANDLE hFile, UUID *a2, __int64 a3, __int64 a4, unsigned int a5)
{
  unsigned int v7; // ebx
  __int64 v8; // rax
  unsigned int v9; // eax
  int v11; // [rsp+20h] [rbp-38h] BYREF
  UUID Uuid; // [rsp+24h] [rbp-34h] BYREF
  unsigned int v13; // [rsp+34h] [rbp-24h]

  Uuid = 0;
  if ( !a4 || !a3 )
    return 87;
  if ( *(_DWORD *)(a3 + 544) + a5 >= *(_DWORD *)(a3 + 544) )
  {
    v13 = a5;
    v11 = 1;
    if ( !a2 )
      goto LABEL_10;
    v8 = *(_QWORD *)&a2->Data1;
    if ( !*(_QWORD *)&a2->Data1 )
      v8 = *(_QWORD *)a2->Data4;
    if ( v8 )
    {
      Uuid = *a2;
    }
    else
    {
LABEL_10:
      UuidCreate(&Uuid);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF__guid_(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          33,
          WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids,
          &Uuid);
    }
    v9 = WriteNewCredentialHistoryRecord(hFile, a4, a5, (__int64)&v11);
    v7 = v9;
    if ( v9 )
      DebugTraceError(v9, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", 2178);
    else
      return 0;
  }
  else
  {
    return 13;
  }
  return v7;
}

```

## disassembly

```asm
0x1800284ac  push    rbx
0x1800284ae  push    rsi
0x1800284af  push    rdi
0x1800284b0  sub     rsp, 40h
0x1800284b4  mov     rax, cs:__security_cookie
0x1800284bb  xor     rax, rsp
0x1800284be  mov     [rsp+58h+var_20], rax
0x1800284c3  xorps   xmm0, xmm0
0x1800284c6  mov     rdi, r9
0x1800284c9  mov     rsi, rcx
0x1800284cc  movdqu  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x1800284d2  test    r9, r9
0x1800284d5  jz      loc_1800285BB
0x1800284db  test    r8, r8
0x1800284de  jz      loc_1800285BB
0x1800284e4  mov     ecx, [r8+220h]
0x1800284eb  mov     ebx, [rsp+58h+arg_20]
0x1800284f2  lea     eax, [rcx+rbx]
0x1800284f5  cmp     eax, ecx
0x1800284f7  jnb     short loc_180028503
0x1800284f9  mov     ebx, 0Dh
0x1800284fe  jmp     loc_1800285B7
0x180028503  mov     [rsp+58h+var_24], ebx
0x180028507  mov     [rsp+58h+var_38], 1
0x18002850f  test    rdx, rdx
0x180028512  jz      short loc_18002853B
0x180028514  mov     rax, [rdx]
0x180028517  sub     rax, cs:qword_180042E10
0x18002851e  jnz     short loc_18002852B
0x180028520  mov     rax, [rdx+8]
0x180028524  sub     rax, cs:qword_180042E18
0x18002852b  test    rax, rax
0x18002852e  jz      short loc_18002853B
0x180028530  movups  xmm0, xmmword ptr [rdx]
0x180028533  movdqu  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x180028539  jmp     short loc_18002857F
0x18002853b  lea     rcx, [rsp+58h+Uuid]; Uuid
0x180028540  call    cs:__imp_UuidCreate
0x180028547  nop     dword ptr [rax+rax+00h]
0x18002854c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028553  lea     rax, WPP_GLOBAL_Control
0x18002855a  cmp     rcx, rax
0x18002855d  jz      short loc_18002857F
0x18002855f  test    byte ptr [rcx+1Ch], 4
0x180028563  jz      short loc_18002857F
0x180028565  mov     rcx, [rcx+10h]
0x180028569  lea     r9, [rsp+58h+Uuid]
0x18002856e  mov     edx, 21h ; '!'
0x180028573  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x18002857a  call    WPP_SF__guid_
0x18002857f  lea     r9, [rsp+58h+var_38]
0x180028584  mov     r8d, ebx
0x180028587  mov     rdx, rdi
0x18002858a  mov     rcx, rsi; hFile
0x18002858d  call    WriteNewCredentialHistoryRecord
0x180028592  mov     ebx, eax
0x180028594  test    eax, eax
0x180028596  jz      short loc_1800285B5
0x180028598  mov     r9d, 882h
0x18002859e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800285a5  lea     rdx, aDwlasterror; "dwLastError"
0x1800285ac  mov     ecx, eax
0x1800285ae  call    DebugTraceError
0x1800285b3  jmp     short loc_1800285B7
0x1800285b5  xor     ebx, ebx
0x1800285b7  mov     eax, ebx
0x1800285b9  jmp     short loc_1800285C0
0x1800285bb  mov     eax, 57h ; 'W'
0x1800285c0  mov     rcx, [rsp+58h+var_20]
0x1800285c5  xor     rcx, rsp; StackCookie
0x1800285c8  call    __security_check_cookie
0x1800285cd  add     rsp, 40h
0x1800285d1  pop     rdi
0x1800285d2  pop     rsi
0x1800285d3  pop     rbx
0x1800285d4  retn
```
