# NcaExpandEnvironmentStrings

- ea: `0x180019178`
- end: `0x18001933b`
- name: `NcaExpandEnvironmentStrings`
- size: `451`
- prototype: `__int64 __fastcall(SIZE_T, WCHAR **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180019520`

## callees

- `0x1800033bc`
- `0x180003770`
- `0x180004f04`
- `0x180019178`
- `0x1800199b4`
- `0x180019ad0`
- `0x180019dac`
- `0x18001abd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192cc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001921c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001926a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001921c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001926a`

## string_xrefs

- `0x1800191e6`: `%systemroot%\system32\WindowsPowershell\v1.0\powershell.exe`
- `0x180019213`: `%systemroot%\system32\WindowsPowershell\v1.0\powershell.exe`
- `0x180019260`: `%systemroot%\system32\WindowsPowershell\v1.0\powershell.exe`

## pseudocode

```c
__int64 __fastcall NcaExpandEnvironmentStrings(SIZE_T a1, WCHAR **a2)
{
  PVOID *v3; // rcx
  DWORD LastError; // ebp
  unsigned int i; // esi
  DWORD v6; // eax
  DWORD v7; // r14d
  int v8; // eax
  unsigned int v9; // edi
  WCHAR *v10; // rax
  WCHAR *v11; // rbx
  const char *v12; // rdi
  __int64 v13; // rdx
  SIZE_T v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = a1;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  LastError = 8;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  v15 = 0;
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 4) != 0 )
    WPP_SF_S(
      v3[2],
      25,
      WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids,
      L"%systemroot%\\system32\\WindowsPowershell\\v1.0\\powershell.exe");
  *a2 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 5 )
    {
      v9 = -2147418113;
      v13 = 2147549183LL;
      goto LABEL_24;
    }
    v6 = ExpandEnvironmentStringsW(L"%systemroot%\\system32\\WindowsPowershell\\v1.0\\powershell.exe", 0, 0);
    v7 = v6;
    if ( !v6 )
    {
      v12 = "ExpandEnvironmentStringsW";
      LastError = GetLastError();
LABEL_21:
      v9 = NcaReportErrorAsWinError("NcaExpandEnvironmentStrings", v12, LastError);
      if ( (v9 & 0x80000000) == 0 )
        return v9;
      goto LABEL_25;
    }
    v8 = NcaSizeTMultiply(v6, 2, &v15);
    v9 = v8;
    if ( v8 < 0 )
    {
      v13 = (unsigned int)v8;
LABEL_24:
      NcaReportReturnError("NcaExpandEnvironmentStrings", v13);
LABEL_25:
      NcaFree(0);
      return (unsigned int)NcaReportReturnError("NcaExpandEnvironmentStrings", v9);
    }
    v10 = (WCHAR *)NcaAlloc(v15);
    v11 = v10;
    if ( !v10 )
    {
      v12 = "NcaAlloc";
      goto LABEL_21;
    }
    if ( v7 == ExpandEnvironmentStringsW(L"%systemroot%\\system32\\WindowsPowershell\\v1.0\\powershell.exe", v10, v7) )
      break;
    NcaFree(v11);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids, v11);
  *a2 = v11;
  return v9;
}

```

## disassembly

```asm
0x180019178  mov     [rsp+arg_8], rbx
0x18001917d  mov     [rsp+arg_10], rbp
0x180019182  mov     [rsp+arg_0], rcx
0x180019187  push    rsi
0x180019188  push    rdi
0x180019189  push    r12
0x18001918b  push    r14
0x18001918d  push    r15
0x18001918f  sub     rsp, 20h
0x180019193  mov     r15, rdx
0x180019196  mov     rcx, cs:WPP_GLOBAL_Control
0x18001919d  lea     r12, WPP_GLOBAL_Control
0x1800191a4  mov     ebp, 8
0x1800191a9  cmp     rcx, r12
0x1800191ac  jz      short loc_1800191CE
0x1800191ae  test    [rcx+1Ch], bpl
0x1800191b2  jz      short loc_1800191CE
0x1800191b4  mov     rcx, [rcx+10h]
0x1800191b8  lea     edx, [rbp+10h]
0x1800191bb  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x1800191c2  call    WPP_SF_
0x1800191c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800191ce  mov     [rsp+48h+arg_0], 0
0x1800191d7  cmp     rcx, r12
0x1800191da  jz      short loc_1800191FE
0x1800191dc  test    byte ptr [rcx+1Ch], 4
0x1800191e0  jz      short loc_1800191FE
0x1800191e2  mov     rcx, [rcx+10h]
0x1800191e6  lea     r9, Src; "%systemroot%\\system32\\WindowsPowershe"...
0x1800191ed  mov     edx, 19h
0x1800191f2  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x1800191f9  call    WPP_SF_S
0x1800191fe  mov     qword ptr [r15], 0
0x180019205  xor     esi, esi
0x180019207  cmp     esi, 5
0x18001920a  jnb     loc_1800192F4
0x180019210  xor     r8d, r8d; nSize
0x180019213  lea     rcx, Src; "%systemroot%\\system32\\WindowsPowershe"...
0x18001921a  xor     edx, edx; lpDst
0x18001921c  call    cs:__imp_ExpandEnvironmentStringsW
0x180019223  nop     dword ptr [rax+rax+00h]
0x180019228  mov     r14d, eax
0x18001922b  test    eax, eax
0x18001922d  jz      loc_1800192C3
0x180019233  mov     ecx, r14d
0x180019236  lea     r8, [rsp+48h+arg_0]
0x18001923b  mov     edx, 2
0x180019240  call    NcaSizeTMultiply
0x180019245  mov     edi, eax
0x180019247  test    eax, eax
0x180019249  js      short loc_1800192BF
0x18001924b  mov     rcx, [rsp+48h+arg_0]
0x180019250  call    NcaAlloc
0x180019255  mov     rbx, rax
0x180019258  test    rax, rax
0x18001925b  jz      short loc_1800192B6
0x18001925d  mov     r8d, r14d; nSize
0x180019260  lea     rcx, Src; "%systemroot%\\system32\\WindowsPowershe"...
0x180019267  mov     rdx, rax; lpDst
0x18001926a  call    cs:__imp_ExpandEnvironmentStringsW
0x180019271  nop     dword ptr [rax+rax+00h]
0x180019276  cmp     r14d, eax
0x180019279  jz      short loc_180019287
0x18001927b  mov     rcx, rbx; lpMem
0x18001927e  call    NcaFree
0x180019283  inc     esi
0x180019285  jmp     short loc_180019207
0x180019287  mov     rcx, cs:WPP_GLOBAL_Control
0x18001928e  cmp     rcx, r12
0x180019291  jz      short loc_1800192B1
0x180019293  test    byte ptr [rcx+1Ch], 4
0x180019297  jz      short loc_1800192B1
0x180019299  mov     rcx, [rcx+10h]
0x18001929d  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x1800192a4  mov     edx, 1Ah
0x1800192a9  mov     r9, rbx
0x1800192ac  call    WPP_SF_S
0x1800192b1  mov     [r15], rbx
0x1800192b4  jmp     short loc_180019321
0x1800192b6  lea     rdi, aNcaalloc; "NcaAlloc"
0x1800192bd  jmp     short loc_1800192DA
0x1800192bf  mov     edx, eax
0x1800192c1  jmp     short loc_1800192FB
0x1800192c3  xor     ebx, ebx
0x1800192c5  lea     rdi, aExpandenvironm; "ExpandEnvironmentStringsW"
0x1800192cc  call    cs:__imp_GetLastError
0x1800192d3  nop     dword ptr [rax+rax+00h]
0x1800192d8  mov     ebp, eax
0x1800192da  mov     r8d, ebp
0x1800192dd  lea     rcx, aNcaexpandenvir; "NcaExpandEnvironmentStrings"
0x1800192e4  mov     rdx, rdi
0x1800192e7  call    NcaReportErrorAsWinError
0x1800192ec  mov     edi, eax
0x1800192ee  test    eax, eax
0x1800192f0  js      short loc_180019309
0x1800192f2  jmp     short loc_180019321
0x1800192f4  mov     edi, 8000FFFFh
0x1800192f9  mov     edx, edi
0x1800192fb  lea     rcx, aNcaexpandenvir; "NcaExpandEnvironmentStrings"
0x180019302  call    NcaReportReturnError
0x180019307  xor     ebx, ebx
0x180019309  mov     rcx, rbx; lpMem
0x18001930c  call    NcaFree
0x180019311  mov     edx, edi
0x180019313  lea     rcx, aNcaexpandenvir; "NcaExpandEnvironmentStrings"
0x18001931a  call    NcaReportReturnError
0x18001931f  mov     edi, eax
0x180019321  mov     rbx, [rsp+48h+arg_8]
0x180019326  mov     eax, edi
0x180019328  mov     rbp, [rsp+48h+arg_10]
0x18001932d  add     rsp, 20h
0x180019331  pop     r15
0x180019333  pop     r14
0x180019335  pop     r12
0x180019337  pop     rdi
0x180019338  pop     rsi
0x180019339  retn
```
