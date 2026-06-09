# SendETWInformation

- ea: `0x180008000`
- end: `0x1800082f3`
- name: `SendETWInformation`
- size: `755`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180014c80`
- `0x180016370`

## callees

- `0x180008000`
- `0x180008300`
- `0x18001d810`
- `0x18001e1b4`

## import_xrefs

- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000806c`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000806c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008101`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008101`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008093`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008093`
- `ntdll!NtQueryInformationProcess` at `0x1800080f0`
- `ntdll!NtQueryInformationProcess` at `0x1800080f0`

## pseudocode

```c
void __fastcall SendETWInformation(char a1, const wchar_t *a2, __int64 a3, int a4, int a5, int a6, int a7)
{
  HANDLE v11; // rdi
  NTSTATUS v12; // esi
  __int64 v13; // r8
  const wchar_t *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rcx
  bool v17; // zf
  int v18; // eax
  ULONG ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+38h] [rbp-C8h] BYREF
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[56]; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwProcessId; // [rsp+B0h] [rbp-50h]
  _BYTE ProcessInformation[4]; // [rsp+E0h] [rbp-20h] BYREF
  int v31; // [rsp+E4h] [rbp-1Ch]
  __int64 v32; // [rsp+E8h] [rbp-18h]
  __int64 v33; // [rsp+F0h] [rbp-10h]
  _BYTE v34[16]; // [rsp+140h] [rbp+40h] BYREF
  const wchar_t *v35; // [rsp+150h] [rbp+50h]
  int v36; // [rsp+158h] [rbp+58h]
  int v37; // [rsp+15Ch] [rbp+5Ch]
  const wchar_t *v38; // [rsp+160h] [rbp+60h]
  int v39; // [rsp+168h] [rbp+68h]
  int v40; // [rsp+16Ch] [rbp+6Ch]
  __int64 v41; // [rsp+170h] [rbp+70h]
  __int64 v42; // [rsp+178h] [rbp+78h]
  int *v43; // [rsp+180h] [rbp+80h]
  __int64 v44; // [rsp+188h] [rbp+88h]
  int *v45; // [rsp+190h] [rbp+90h]
  __int64 v46; // [rsp+198h] [rbp+98h]
  int *v47; // [rsp+1A0h] [rbp+A0h]
  __int64 v48; // [rsp+1A8h] [rbp+A8h]
  __int64 *v49; // [rsp+1B0h] [rbp+B0h]
  __int64 v50; // [rsp+1B8h] [rbp+B8h]
  int *v51; // [rsp+1C0h] [rbp+C0h]
  __int64 v52; // [rsp+1C8h] [rbp+C8h]
  __int64 *v53; // [rsp+1D0h] [rbp+D0h]
  __int64 v54; // [rsp+1D8h] [rbp+D8h]
  int *v55; // [rsp+1E0h] [rbp+E0h]
  __int64 v56; // [rsp+1E8h] [rbp+E8h]

  if ( (byte_18004CC41 & 8) != 0 )
  {
    memset_0(v28, 0, 0x68u);
    RpcCallAttributes[0] = 2;
    RpcCallAttributes[1] = 16;
    if ( RpcServerInqCallAttributesW(0, RpcCallAttributes) >= 0 )
    {
      v11 = OpenProcess(0x1000u, 0, dwProcessId);
      if ( v11 )
      {
        ReturnLength = 0;
        memset_0(ProcessInformation, 0, 0x60u);
        v12 = NtQueryInformationProcess(v11, (PROCESSINFOCLASS)64, ProcessInformation, 0x60u, &ReturnLength);
        CloseHandle(v11);
        if ( ((int)(v12 + 0x80000000) < 0 || v12 == -2147483643) && (byte_18004CC41 & 8) != 0 )
        {
          v20 = a4;
          v14 = L"SPCryptProtect";
          if ( !a1 )
            v14 = L"SPCryptUnprotect";
          v24 = a7;
          v26 = v33;
          v23 = v31;
          v25 = v32;
          v22 = a6;
          v21 = a5;
          v15 = -1;
          v16 = -1;
          do
            v17 = v14[++v16] == 0;
          while ( !v17 );
          v35 = v14;
          v36 = 2 * v16 + 2;
          v37 = 0;
          if ( a2 )
          {
            do
              v17 = a2[++v15] == 0;
            while ( !v17 );
            v18 = 2 * v15 + 2;
          }
          else
          {
            v18 = 10;
          }
          v39 = v18;
          v40 = 0;
          v43 = &v20;
          v41 = a3;
          v45 = &v21;
          v42 = 16;
          v47 = &v22;
          if ( !a2 )
            a2 = L"NULL";
          v38 = a2;
          v49 = &v25;
          v44 = 4;
          v51 = &v23;
          v53 = &v26;
          v55 = &v24;
          v46 = 4;
          v48 = 4;
          v50 = 8;
          v52 = 4;
          v54 = 8;
          v56 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            (__int64)L"NULL",
            (__int64)ETW_LOG_DEF_INFORMATION,
            v13,
            11,
            (__int64)v34);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180008000  push    rbp
0x180008002  push    rbx
0x180008003  push    r12
0x180008005  push    r14
0x180008007  push    r15
0x180008009  lea     rbp, [rsp-100h]
0x180008011  sub     rsp, 200h
0x180008018  mov     rax, cs:__security_cookie
0x18000801f  xor     rax, rsp
0x180008022  mov     [rbp+120h+var_30], rax
0x180008029  test    cs:byte_18004CC41, 8
0x180008030  mov     r14d, r9d
0x180008033  mov     r12, r8
0x180008036  mov     rbx, rdx
0x180008039  movzx   r15d, cl
0x18000803d  jz      loc_18000813A
0x180008043  xor     edx, edx; Val
0x180008045  lea     rcx, [rsp+220h+var_1A8]; void *
0x18000804a  mov     r8d, 68h ; 'h'; Size
0x180008050  call    memset_0
0x180008055  lea     rdx, [rsp+220h+RpcCallAttributes]; RpcCallAttributes
0x18000805a  mov     [rsp+220h+RpcCallAttributes], 2
0x180008062  xor     ecx, ecx; ClientBinding
0x180008064  mov     [rsp+220h+var_1AC], 10h
0x18000806c  call    cs:__imp_RpcServerInqCallAttributesW
0x180008073  nop     dword ptr [rax+rax+00h]
0x180008078  test    eax, eax
0x18000807a  js      loc_18000813A
0x180008080  mov     r8d, [rbp+120h+dwProcessId]; dwProcessId
0x180008084  xor     edx, edx; bInheritHandle
0x180008086  mov     ecx, 1000h; dwDesiredAccess
0x18000808b  mov     [rsp+220h+arg_8], rdi
0x180008093  call    cs:__imp_OpenProcess
0x18000809a  nop     dword ptr [rax+rax+00h]
0x18000809f  mov     rdi, rax
0x1800080a2  test    rax, rax
0x1800080a5  jz      loc_180008132
0x1800080ab  mov     [rsp+220h+arg_0], rsi
0x1800080b3  lea     rcx, [rbp+120h+ProcessInformation]; void *
0x1800080b7  mov     [rsp+220h+arg_10], r13
0x1800080bf  xor     edx, edx; Val
0x1800080c1  xor     r13d, r13d
0x1800080c4  mov     r8d, 60h ; '`'; Size
0x1800080ca  mov     [rsp+220h+var_1F0], r13d
0x1800080cf  call    memset_0
0x1800080d4  lea     rax, [rsp+220h+var_1F0]
0x1800080d9  mov     r9d, 60h ; '`'; ProcessInformationLength
0x1800080df  lea     r8, [rbp+120h+ProcessInformation]; ProcessInformation
0x1800080e3  mov     [rsp+220h+ReturnLength], rax; ReturnLength
0x1800080e8  mov     edx, 40h ; '@'; ProcessInformationClass
0x1800080ed  mov     rcx, rdi; ProcessHandle
0x1800080f0  call    cs:__imp_NtQueryInformationProcess
0x1800080f7  nop     dword ptr [rax+rax+00h]
0x1800080fc  mov     rcx, rdi; hObject
0x1800080ff  mov     esi, eax
0x180008101  call    cs:__imp_CloseHandle
0x180008108  nop     dword ptr [rax+rax+00h]
0x18000810d  mov     eax, 80000000h
0x180008112  lea     ecx, [rsi+rax]
0x180008115  test    eax, ecx
0x180008117  jz      short loc_18000815A
0x180008119  test    cs:byte_18004CC41, 8
0x180008120  jnz     short loc_180008164
0x180008122  mov     rsi, [rsp+220h+arg_0]
0x18000812a  mov     r13, [rsp+220h+arg_10]
0x180008132  mov     rdi, [rsp+220h+arg_8]
0x18000813a  mov     rcx, [rbp+120h+var_30]
0x180008141  xor     rcx, rsp; StackCookie
0x180008144  call    __security_check_cookie
0x180008149  add     rsp, 200h
0x180008150  pop     r15
0x180008152  pop     r14
0x180008154  pop     r12
0x180008156  pop     rbx
0x180008157  pop     rbp
0x180008158  retn
0x18000815a  cmp     esi, 80000005h
0x180008160  jz      short loc_180008119
0x180008162  jmp     short loc_180008122
0x180008164  lea     rax, aSpcryptunprote; "SPCryptUnprotect"
0x18000816b  mov     [rsp+220h+var_1E8], r14d
0x180008170  test    r15b, r15b
0x180008173  lea     rdx, aSpcryptprotect; "SPCryptProtect"
0x18000817a  cmovz   rdx, rax
0x18000817e  mov     eax, [rbp+120h+arg_30]
0x180008184  mov     [rsp+220h+var_1C8], eax
0x180008188  mov     rax, [rbp+120h+var_130]
0x18000818c  mov     [rsp+220h+var_1B8], rax
0x180008191  mov     eax, [rbp+120h+var_13C]
0x180008194  mov     [rsp+220h+var_1D0], eax
0x180008198  mov     rax, [rbp+120h+var_138]
0x18000819c  mov     [rsp+220h+var_1C0], rax
0x1800081a1  mov     eax, [rbp+120h+arg_28]
0x1800081a7  mov     [rsp+220h+var_1D8], eax
0x1800081ab  mov     eax, [rbp+120h+arg_20]
0x1800081b1  mov     [rsp+220h+var_1E0], eax
0x1800081b5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800081bc  mov     rcx, rax
0x1800081bf  nop
0x1800081c0  cmp     [rdx+rcx*2+2], r13w
0x1800081c6  lea     rcx, [rcx+1]
0x1800081ca  jnz     short loc_1800081C0
0x1800081cc  mov     [rbp+120h+var_D0], rdx
0x1800081d0  lea     ecx, ds:2[rcx*2]
0x1800081d7  mov     [rbp+120h+var_C8], ecx
0x1800081da  mov     [rbp+120h+var_C4], r13d
0x1800081de  test    rbx, rbx
0x1800081e1  jz      loc_1800082E9
0x1800081e7  nop     word ptr [rax+rax+00000000h]
0x1800081f0  cmp     [rbx+rax*2+2], r13w
0x1800081f6  lea     rax, [rax+1]
0x1800081fa  jnz     short loc_1800081F0
0x1800081fc  lea     eax, ds:2[rax*2]
0x180008203  mov     [rbp+120h+var_B8], eax
0x180008206  lea     rcx, aNull_0; "NULL"
0x18000820d  lea     rax, [rsp+220h+var_1E8]
0x180008212  mov     [rbp+120h+var_B4], r13d
0x180008216  mov     [rbp+120h+var_A0], rax
0x18000821d  lea     rdx, ETW_LOG_DEF_INFORMATION
0x180008224  lea     rax, [rsp+220h+var_1E0]
0x180008229  mov     [rbp+120h+var_B0], r12
0x18000822d  mov     [rbp+120h+var_90], rax
0x180008234  test    rbx, rbx
0x180008237  lea     rax, [rsp+220h+var_1D8]
0x18000823c  mov     [rbp+120h+var_A8], 10h
0x180008244  mov     [rbp+120h+var_80], rax
0x18000824b  cmovz   rbx, rcx
0x18000824f  lea     rax, [rsp+220h+var_1C0]
0x180008254  mov     [rbp+120h+var_C0], rbx
0x180008258  mov     [rbp+120h+var_70], rax
0x18000825f  mov     r9d, 0Bh
0x180008265  lea     rax, [rsp+220h+var_1D0]
0x18000826a  mov     [rbp+120h+var_98], 4
0x180008275  mov     [rbp+120h+var_60], rax
0x18000827c  lea     rax, [rsp+220h+var_1B8]
0x180008281  mov     [rbp+120h+var_50], rax
0x180008288  lea     rax, [rsp+220h+var_1C8]
0x18000828d  mov     [rbp+120h+var_40], rax
0x180008294  lea     rax, [rbp+120h+var_E0]
0x180008298  mov     [rsp+220h+ReturnLength], rax
0x18000829d  mov     [rbp+120h+var_88], 4
0x1800082a8  mov     [rbp+120h+var_78], 4
0x1800082b3  mov     [rbp+120h+var_68], 8
0x1800082be  mov     [rbp+120h+var_58], 4
0x1800082c9  mov     [rbp+120h+var_48], 8
0x1800082d4  mov     [rbp+120h+var_38], 4
0x1800082df  call    McGenEventWrite_EtwEventWriteTransfer
0x1800082e4  jmp     loc_180008122
0x1800082e9  mov     eax, 0Ah
0x1800082ee  jmp     loc_180008203
```
