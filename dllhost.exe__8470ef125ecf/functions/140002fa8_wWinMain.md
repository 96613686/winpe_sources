# wWinMain

- ea: `0x140002fa8`
- end: `0x1400031a4`
- name: `wWinMain`
- size: `508`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400011d0`

## callees

- `0x140001380`
- `0x140002f5c`
- `0x140002fa8`
- `0x1400032a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000306b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000306b`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterSurrogateEx` at `0x14000316a`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterSurrogateEx` at `0x14000316a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140003111`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140003111`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140003176`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140003176`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140003181`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140003181`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1400030c2`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1400030c2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003159`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003159`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003170`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003170`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140003144`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140003144`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140002fdc`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140002fdc`

## string_xrefs

- `0x140003060`: `/ProcessID`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  _WORD *v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // rcx
  _WORD *v9; // rcx
  OLECHAR v10; // ax
  _WORD *v11; // rcx
  OLECHAR *v12; // rbx
  __int64 v13; // rdx
  OLECHAR *v14; // rax
  OLECHAR *v15; // rcx
  unsigned int v16; // r8d
  const char *v17; // r9
  __int64 v18; // rdx
  HANDLE CurrentProcess; // rax
  int TokenInformation; // [rsp+30h] [rbp-D0h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-CCh] BYREF
  int v23; // [rsp+38h] [rbp-C8h] BYREF
  IID iid; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[48]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v26[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  v5 = v26;
  v6 = 2147483646;
  v7 = 261;
  iid = 0;
  v8 = 2147483646;
  do
  {
    if ( !v8 )
      break;
    if ( !*lpCmdLine )
      break;
    *v5++ = *lpCmdLine++;
    --v8;
    --v7;
  }
  while ( v7 );
  v9 = v5 - 1;
  if ( v7 )
    v9 = v5;
  *v9 = 0;
  if ( v7 )
  {
    v10 = v26[0];
    if ( !v26[0] )
      goto LABEL_15;
    v11 = v26;
    while ( 1 )
    {
      v12 = v11 + 1;
      if ( v10 == 58 )
        break;
      v10 = *v12;
      ++v11;
      if ( !*v12 )
        goto LABEL_15;
    }
    *v11 = 0;
    if ( !*v12 || (unsigned int)_o__wcsicmp(v26, L"/ProcessID") )
LABEL_15:
      v12 = v26;
    v13 = 41;
    v14 = sz;
    do
    {
      if ( !v6 )
        break;
      if ( !*v12 )
        break;
      *v14++ = *v12++;
      --v6;
      --v13;
    }
    while ( v13 );
    v15 = v14 - 1;
    if ( v13 )
      v15 = v14;
    *v15 = 0;
    if ( v13 )
    {
      if ( IIDFromString(sz, &iid) >= 0 )
      {
        if ( !memcmp_0(&iid, qword_140005698, 0x10u) )
        {
          TokenInformation = 0;
          ReturnLength = 4;
          if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenElevation, &TokenInformation, 4u, &ReturnLength) )
          {
            v18 = 125;
            return wil::details::in1diag3::Win32_Return_GetLastError(retaddr, (void *)v18, v16, v17);
          }
          if ( TokenInformation )
          {
            v23 = 1;
            if ( !(unsigned int)SetProcessMitigationPolicy(16, &v23, 4) )
            {
              v18 = 134;
              return wil::details::in1diag3::Win32_Return_GetLastError(retaddr, (void *)v18, v16, v17);
            }
          }
        }
        if ( CoInitializeEx(0, 0) >= 0 )
        {
          CoRegisterSurrogateEx(&iid, 0);
          CoUninitialize();
          CurrentProcess = GetCurrentProcess();
          TerminateProcess(CurrentProcess, 0);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140002fa8  push    rbp
0x140002faa  push    rbx
0x140002fab  push    rsi
0x140002fac  push    rdi
0x140002fad  lea     rbp, [rsp-1D8h]
0x140002fb5  sub     rsp, 2D8h
0x140002fbc  mov     rax, cs:__security_cookie
0x140002fc3  xor     rax, rsp
0x140002fc6  mov     [rbp+1F0h+var_30], rax
0x140002fcd  xor     r9d, r9d; HeapInformationLength
0x140002fd0  mov     rbx, r8
0x140002fd3  xor     r8d, r8d; HeapInformation
0x140002fd6  xor     ecx, ecx; HeapHandle
0x140002fd8  lea     edx, [r9+1]; HeapInformationClass
0x140002fdc  call    cs:__imp_HeapSetInformation
0x140002fe2  xorps   xmm0, xmm0
0x140002fe5  lea     rax, [rbp+1F0h+var_240]
0x140002fe9  mov     edi, 7FFFFFFEh
0x140002fee  mov     edx, 105h
0x140002ff3  movups  xmmword ptr [rsp+2F0h+iid.Data1], xmm0
0x140002ff8  mov     ecx, edi
0x140002ffa  xor     esi, esi
0x140002ffc  test    rcx, rcx
0x140002fff  jz      short loc_140003020
0x140003001  movzx   r8d, word ptr [rbx]
0x140003005  test    r8w, r8w
0x140003009  jz      short loc_140003020
0x14000300b  mov     [rax], r8w
0x14000300f  add     rbx, 2
0x140003013  add     rax, 2
0x140003017  dec     rcx
0x14000301a  sub     rdx, 1
0x14000301e  jnz     short loc_140002FFC
0x140003020  test    rdx, rdx
0x140003023  lea     rcx, [rax-2]
0x140003027  cmovnz  rcx, rax
0x14000302b  mov     [rcx], si
0x14000302e  jz      loc_140003187
0x140003034  movzx   eax, [rbp+1F0h+var_240]
0x140003038  test    ax, ax
0x14000303b  jz      short loc_140003075
0x14000303d  lea     rcx, [rbp+1F0h+var_240]
0x140003041  lea     rbx, [rcx+2]
0x140003045  cmp     ax, 3Ah ; ':'
0x140003049  jz      short loc_140003058
0x14000304b  movzx   eax, word ptr [rbx]
0x14000304e  mov     rcx, rbx
0x140003051  test    ax, ax
0x140003054  jnz     short loc_140003041
0x140003056  jmp     short loc_140003075
0x140003058  mov     [rcx], si
0x14000305b  cmp     [rbx], si
0x14000305e  jz      short loc_140003075
0x140003060  lea     rdx, aProcessid; "/ProcessID"
0x140003067  lea     rcx, [rbp+1F0h+var_240]
0x14000306b  call    cs:__imp__o__wcsicmp
0x140003071  test    eax, eax
0x140003073  jz      short loc_140003079
0x140003075  lea     rbx, [rbp+1F0h+var_240]
0x140003079  mov     edx, 29h ; ')'
0x14000307e  lea     rax, [rsp+2F0h+sz]
0x140003083  test    rdi, rdi
0x140003086  jz      short loc_1400030A4
0x140003088  movzx   ecx, word ptr [rbx]
0x14000308b  test    cx, cx
0x14000308e  jz      short loc_1400030A4
0x140003090  mov     [rax], cx
0x140003093  add     rbx, 2
0x140003097  add     rax, 2
0x14000309b  dec     rdi
0x14000309e  sub     rdx, 1
0x1400030a2  jnz     short loc_140003083
0x1400030a4  test    rdx, rdx
0x1400030a7  lea     rcx, [rax-2]
0x1400030ab  cmovnz  rcx, rax
0x1400030af  mov     [rcx], si
0x1400030b2  jz      loc_140003187
0x1400030b8  lea     rdx, [rsp+2F0h+iid]; lpiid
0x1400030bd  lea     rcx, [rsp+2F0h+sz]; lpsz
0x1400030c2  call    cs:__imp_IIDFromString
0x1400030c8  test    eax, eax
0x1400030ca  js      loc_140003187
0x1400030d0  mov     edi, 10h
0x1400030d5  lea     rdx, qword_140005698; Buf2
0x1400030dc  mov     r8d, edi; Size
0x1400030df  lea     rcx, [rsp+2F0h+iid]; Buf1
0x1400030e4  call    memcmp_0
0x1400030e9  test    eax, eax
0x1400030eb  jnz     short loc_140003155
0x1400030ed  lea     ebx, [rdi-0Ch]
0x1400030f0  mov     [rsp+2F0h+TokenInformation], esi
0x1400030f4  lea     rax, [rsp+2F0h+var_2BC]
0x1400030f9  mov     [rsp+2F0h+var_2BC], ebx
0x1400030fd  mov     r9d, ebx; TokenInformationLength
0x140003100  mov     [rsp+2F0h+ReturnLength], rax; ReturnLength
0x140003105  lea     r8, [rsp+2F0h+TokenInformation]; TokenInformation
0x14000310a  lea     edx, [rdi+4]; TokenInformationClass
0x14000310d  lea     rcx, [rdi-14h]; TokenHandle
0x140003111  call    cs:__imp_GetTokenInformation
0x140003117  test    eax, eax
0x140003119  jnz     short loc_14000312C
0x14000311b  lea     edx, [rdi+6Dh]; void *
0x14000311e  mov     rcx, [rbp+1F8h]; this
0x140003125  call    ?Win32_Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Win32_Return_GetLastError(void *,uint,char const *)
0x14000312a  jmp     short loc_140003189
0x14000312c  cmp     [rsp+2F0h+TokenInformation], esi
0x140003130  jz      short loc_140003155
0x140003132  mov     r8, rbx
0x140003135  mov     [rsp+2F0h+var_2B8], 1
0x14000313d  lea     rdx, [rsp+2F0h+var_2B8]
0x140003142  mov     ecx, edi
0x140003144  call    cs:__imp_SetProcessMitigationPolicy
0x14000314a  test    eax, eax
0x14000314c  jnz     short loc_140003155
0x14000314e  mov     edx, 86h
0x140003153  jmp     short loc_14000311E
0x140003155  xor     edx, edx; dwCoInit
0x140003157  xor     ecx, ecx; pvReserved
0x140003159  call    cs:__imp_CoInitializeEx
0x14000315f  test    eax, eax
0x140003161  js      short loc_140003187
0x140003163  xor     edx, edx
0x140003165  lea     rcx, [rsp+2F0h+iid]
0x14000316a  call    cs:__imp_CoRegisterSurrogateEx
0x140003170  call    cs:__imp_CoUninitialize
0x140003176  call    cs:__imp_GetCurrentProcess
0x14000317c  mov     rcx, rax; hProcess
0x14000317f  xor     edx, edx; uExitCode
0x140003181  call    cs:__imp_TerminateProcess
0x140003187  xor     eax, eax
0x140003189  mov     rcx, [rbp+1F0h+var_30]
0x140003190  xor     rcx, rsp; StackCookie
0x140003193  call    __security_check_cookie
0x140003198  add     rsp, 2D8h
0x14000319f  pop     rdi
0x1400031a0  pop     rsi
0x1400031a1  pop     rbx
0x1400031a2  pop     rbp
0x1400031a3  retn
```
