# LdrpResolveProcedureAddress

- ea: `0x180053390`
- end: `0x1800535b6`
- name: `LdrpResolveProcedureAddress`
- size: `550`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x180052930`
- `0x180054da0`

## callees

- `0x18001e820`
- `0x180022aa0`
- `0x180029120`
- `0x18002c6f0`
- `0x180050ed0`
- `0x180053390`
- `0x180054000`
- `0x1800ac994`
- `0x1800bcba0`
- `0x1800c54a0`
- `0x1800fdad0`
- `0x18012b9f0`
- `0x180162000`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall LdrpResolveProcedureAddress(
        __int64 a1,
        __int64 a2,
        const char *a3,
        ULONG a4,
        char a5,
        unsigned __int64 *a6)
{
  __int64 v8; // rbx
  int *v10; // rcx
  unsigned int v11; // r14d
  char ShouldModuleImportBeRedirected; // al
  int ProcedureAddress; // eax
  __int64 v14; // rdx
  int v15; // ebx
  __int64 v16; // rax
  __int64 v18; // rcx
  char *v19; // rbx
  char *v20; // rax
  char *v21; // rdi
  unsigned __int64 v22; // rax
  __int64 v23; // rax
  char v24; // [rsp+30h] [rbp-B9h]
  __int64 v25; // [rsp+38h] [rbp-B1h] BYREF
  ULONG Value; // [rsp+40h] [rbp-A9h] BYREF
  STRING SourceString; // [rsp+48h] [rbp-A1h] BYREF
  __int64 v28; // [rsp+58h] [rbp-91h]
  __int64 v29[3]; // [rsp+60h] [rbp-89h] BYREF
  int v30; // [rsp+78h] [rbp-71h]

  v28 = a1;
  v8 = a1;
  memset_thunk_772440563353939046(v29, 0, 0x80u);
  v10 = *(int **)(a2 + 80);
  Value = a4;
  v11 = 0;
  v25 = a2;
  SourceString = 0;
  LdrpInitializeDllPath(v10, 1, v29);
  ShouldModuleImportBeRedirected = LdrpShouldModuleImportBeRedirected(v8);
  v24 = ShouldModuleImportBeRedirected;
  while ( 1 )
  {
    if ( ShouldModuleImportBeRedirected )
    {
      if ( a3 )
      {
        v23 = LdrpCheckRedirection(v8, v25, a3);
        if ( v23 != -4530927 )
        {
          *a6 = v23;
          return 0;
        }
      }
    }
    ProcedureAddress = LdrpGetProcedureAddress(*(_QWORD *)(v25 + 48), a3, a4, a6);
    v15 = ProcedureAddress;
    if ( ProcedureAddress != -1073741267 )
      break;
    if ( v11 >= 0x20
      || (a5 & 2) != 0
      || (v19 = (char *)*a6, v20 = strrchr((const char *)*a6, 46), (v21 = v20) == 0)
      || (v22 = v20 - v19, v22 > 0xFFFF) )
    {
LABEL_21:
      v15 = -1073741701;
      goto LABEL_5;
    }
    a3 = v21 + 1;
    SourceString.Buffer = v19;
    SourceString.Length = v22;
    SourceString.MaximumLength = v22;
    if ( *a3 == 35 )
    {
      if ( RtlCharToInteger(a3 + 1, 0, &Value) < 0 )
        goto LABEL_21;
      a4 = Value;
      a3 = 0;
    }
    v30 = *(_DWORD *)(v25 + 272);
    v15 = LdrpLoadForwardedDll(&SourceString, (int)v29, a2, v25, 2, &v25);
    if ( v15 < 0 )
      goto LABEL_5;
    LdrpDereferenceModule(v25);
    ShouldModuleImportBeRedirected = v24;
    ++v11;
    v8 = v28;
  }
  if ( (a5 & 1) != 0 && ProcedureAddress >= 0 )
  {
    if ( (a5 & 2) != 0 )
    {
      v18 = *(_QWORD *)(v25 + 184);
      LOBYTE(v14) = 1;
    }
    else
    {
      v18 = *(_QWORD *)(v25 + 48);
      v14 = 0;
    }
    RtlGuardCheckImageBase(v18, v14);
  }
LABEL_5:
  LdrpReleaseDllPath((__int64)v29);
  if ( v15 < 0 )
    v16 = 0;
  else
    v16 = RtlpHpRedirectHeapExport(*a6);
  *a6 = v16;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180053390  push    rbp
0x180053392  push    rbx
0x180053393  push    rsi
0x180053394  push    rdi
0x180053395  push    r12
0x180053397  push    r13
0x180053399  push    r14
0x18005339b  push    r15
0x18005339d  lea     rbp, [rsp-0Fh]
0x1800533a2  sub     rsp, 0F8h
0x1800533a9  mov     rax, cs:__security_cookie
0x1800533b0  xor     rax, rsp
0x1800533b3  mov     [rbp+47h+var_50], rax
0x1800533b7  mov     rsi, [rbp+47h+arg_28]
0x1800533bb  mov     rdi, r8
0x1800533be  mov     r13, rdx
0x1800533c1  mov     [rsp+130h+var_D8], rcx
0x1800533c6  mov     rbx, rcx
0x1800533c9  xor     edx, edx; Val
0x1800533cb  mov     r8d, 80h; Size
0x1800533d1  lea     rcx, [rsp+130h+var_D0]; void *
0x1800533d6  mov     r12d, r9d
0x1800533d9  call    memset$thunk$772440563353939046
0x1800533de  mov     rcx, [r13+50h]
0x1800533e2  lea     r8, [rsp+130h+var_D0]
0x1800533e7  xorps   xmm0, xmm0
0x1800533ea  mov     [rsp+130h+Value], r12d
0x1800533ef  xor     r14d, r14d
0x1800533f2  mov     [rsp+130h+var_F8], r13
0x1800533f7  movups  xmmword ptr [rsp+130h+SourceString.Length], xmm0
0x1800533fc  lea     edx, [r14+1]
0x180053400  call    LdrpInitializeDllPath
0x180053405  mov     rcx, rbx
0x180053408  call    LdrpShouldModuleImportBeRedirected
0x18005340d  mov     r15d, dword ptr [rbp+47h+arg_20]
0x180053411  and     r15d, 2
0x180053415  mov     [rsp+130h+var_100], al
0x180053419  test    al, al
0x18005341b  jnz     loc_180053579
0x180053421  mov     rcx, [rsp+130h+var_F8]
0x180053426  mov     r9, rsi
0x180053429  mov     r8d, r12d
0x18005342c  mov     rdx, rdi
0x18005342f  mov     rcx, [rcx+30h]
0x180053433  call    LdrpGetProcedureAddress
0x180053438  mov     ebx, eax
0x18005343a  cmp     eax, 0C000022Dh
0x18005343f  jz      short loc_1800534A6
0x180053441  test    [rbp+47h+arg_20], 1
0x180053445  jnz     short loc_180053487
0x180053447  lea     rcx, [rsp+130h+var_D0]
0x18005344c  call    LdrpReleaseDllPath
0x180053451  test    ebx, ebx
0x180053453  js      short loc_180053483
0x180053455  mov     rcx, [rsi]
0x180053458  call    RtlpHpRedirectHeapExport
0x18005345d  mov     [rsi], rax
0x180053460  mov     eax, ebx
0x180053462  mov     rcx, [rbp+47h+var_50]
0x180053466  xor     rcx, rsp; StackCookie
0x180053469  call    __security_check_cookie
0x18005346e  add     rsp, 0F8h
0x180053475  pop     r15
0x180053477  pop     r14
0x180053479  pop     r13
0x18005347b  pop     r12
0x18005347d  pop     rdi
0x18005347e  pop     rsi
0x18005347f  pop     rbx
0x180053480  pop     rbp
0x180053481  retn
0x180053483  xor     eax, eax
0x180053485  jmp     short loc_18005345D
0x180053487  test    eax, eax
0x180053489  js      short loc_180053447
0x18005348b  mov     rcx, [rsp+130h+var_F8]
0x180053490  test    r15d, r15d
0x180053493  jnz     loc_1800535A8
0x180053499  mov     rcx, [rcx+30h]
0x18005349d  xor     edx, edx
0x18005349f  call    RtlGuardCheckImageBase
0x1800534a4  jmp     short loc_180053447
0x1800534a6  cmp     r14d, 20h ; ' '
0x1800534aa  jnb     loc_180053566
0x1800534b0  test    r15d, r15d
0x1800534b3  jnz     loc_180053566
0x1800534b9  mov     rbx, [rsi]
0x1800534bc  lea     edx, [r15+2Eh]; Ch
0x1800534c0  mov     rcx, rbx; Str
0x1800534c3  call    strrchr
0x1800534c8  mov     rdi, rax
0x1800534cb  test    rax, rax
0x1800534ce  jz      loc_180053566
0x1800534d4  sub     rax, rbx
0x1800534d7  cmp     rax, 0FFFFh
0x1800534dd  ja      loc_180053566
0x1800534e3  inc     rdi
0x1800534e6  mov     [rsp+130h+SourceString.Buffer], rbx
0x1800534eb  mov     [rsp+130h+SourceString.Length], ax
0x1800534f0  mov     [rsp+130h+SourceString.MaximumLength], ax
0x1800534f5  cmp     byte ptr [rdi], 23h ; '#'
0x1800534f8  jz      short loc_180053552
0x1800534fa  mov     r9, [rsp+130h+var_F8]
0x1800534ff  lea     rdx, [rsp+130h+var_D0]
0x180053504  mov     r8, r13
0x180053507  lea     rcx, [rsp+130h+SourceString]; SourceString
0x18005350c  mov     eax, [r9+110h]
0x180053513  mov     [rbp+47h+var_B8], eax
0x180053516  lea     rax, [rsp+130h+var_F8]
0x18005351b  mov     [rsp+130h+var_108], rax; __int64
0x180053520  mov     [rsp+130h+var_110], 2; int
0x180053528  call    LdrpLoadForwardedDll
0x18005352d  mov     ebx, eax
0x18005352f  test    eax, eax
0x180053531  js      loc_180053447
0x180053537  mov     rcx, [rsp+130h+var_F8]
0x18005353c  call    LdrpDereferenceModule
0x180053541  mov     al, [rsp+130h+var_100]
0x180053545  inc     r14d
0x180053548  mov     rbx, [rsp+130h+var_D8]
0x18005354d  jmp     loc_180053419
0x180053552  lea     rcx, [rdi+1]; String
0x180053556  xor     edx, edx; Base
0x180053558  lea     r8, [rsp+130h+Value]; Value
0x18005355d  call    RtlCharToInteger
0x180053562  test    eax, eax
0x180053564  jns     short loc_180053570
0x180053566  mov     ebx, 0C000007Bh
0x18005356b  jmp     loc_180053447
0x180053570  mov     r12d, [rsp+130h+Value]
0x180053575  xor     edi, edi
0x180053577  jmp     short loc_1800534FA
0x180053579  test    rdi, rdi
0x18005357c  jz      loc_180053421
0x180053582  mov     rdx, [rsp+130h+var_F8]
0x180053587  mov     r8, rdi
0x18005358a  mov     rcx, rbx
0x18005358d  call    LdrpCheckRedirection
0x180053592  cmp     rax, 0FFFFFFFFFFBADD11h
0x180053598  jz      loc_180053421
0x18005359e  mov     [rsi], rax
0x1800535a1  xor     eax, eax
0x1800535a3  jmp     loc_180053462
0x1800535a8  mov     rcx, [rcx+0B8h]
0x1800535af  mov     dl, 1
0x1800535b1  jmp     loc_18005349F
```
