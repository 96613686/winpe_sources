# LdrpResolveProcedureAddress

- ea: `0x18006fd70`
- end: `0x18006ff96`
- name: `LdrpResolveProcedureAddress`
- size: `550`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x18006f310`
- `0x180071780`

## callees

- `0x18001e820`
- `0x180022a90`
- `0x180029010`
- `0x18002b9f0`
- `0x18006d8b0`
- `0x18006fd70`
- `0x1800709e0`
- `0x1800b74cc`
- `0x1800c0e80`
- `0x1800c8f70`
- `0x1800fe0f0`
- `0x18012c4e0`
- `0x180162810`
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
0x18006fd70  push    rbp
0x18006fd72  push    rbx
0x18006fd73  push    rsi
0x18006fd74  push    rdi
0x18006fd75  push    r12
0x18006fd77  push    r13
0x18006fd79  push    r14
0x18006fd7b  push    r15
0x18006fd7d  lea     rbp, [rsp-0Fh]
0x18006fd82  sub     rsp, 0F8h
0x18006fd89  mov     rax, cs:__security_cookie
0x18006fd90  xor     rax, rsp
0x18006fd93  mov     [rbp+47h+var_50], rax
0x18006fd97  mov     rsi, [rbp+47h+arg_28]
0x18006fd9b  mov     rdi, r8
0x18006fd9e  mov     r13, rdx
0x18006fda1  mov     [rsp+130h+var_D8], rcx
0x18006fda6  mov     rbx, rcx
0x18006fda9  xor     edx, edx; Val
0x18006fdab  mov     r8d, 80h; Size
0x18006fdb1  lea     rcx, [rsp+130h+var_D0]; void *
0x18006fdb6  mov     r12d, r9d
0x18006fdb9  call    memset$thunk$772440563353939046
0x18006fdbe  mov     rcx, [r13+50h]
0x18006fdc2  lea     r8, [rsp+130h+var_D0]
0x18006fdc7  xorps   xmm0, xmm0
0x18006fdca  mov     [rsp+130h+Value], r12d
0x18006fdcf  xor     r14d, r14d
0x18006fdd2  mov     [rsp+130h+var_F8], r13
0x18006fdd7  movups  xmmword ptr [rsp+130h+SourceString.Length], xmm0
0x18006fddc  lea     edx, [r14+1]
0x18006fde0  call    LdrpInitializeDllPath
0x18006fde5  mov     rcx, rbx
0x18006fde8  call    LdrpShouldModuleImportBeRedirected
0x18006fded  mov     r15d, dword ptr [rbp+47h+arg_20]
0x18006fdf1  and     r15d, 2
0x18006fdf5  mov     [rsp+130h+var_100], al
0x18006fdf9  test    al, al
0x18006fdfb  jnz     loc_18006FF59
0x18006fe01  mov     rcx, [rsp+130h+var_F8]
0x18006fe06  mov     r9, rsi
0x18006fe09  mov     r8d, r12d
0x18006fe0c  mov     rdx, rdi
0x18006fe0f  mov     rcx, [rcx+30h]
0x18006fe13  call    LdrpGetProcedureAddress
0x18006fe18  mov     ebx, eax
0x18006fe1a  cmp     eax, 0C000022Dh
0x18006fe1f  jz      short loc_18006FE86
0x18006fe21  test    [rbp+47h+arg_20], 1
0x18006fe25  jnz     short loc_18006FE67
0x18006fe27  lea     rcx, [rsp+130h+var_D0]
0x18006fe2c  call    LdrpReleaseDllPath
0x18006fe31  test    ebx, ebx
0x18006fe33  js      short loc_18006FE63
0x18006fe35  mov     rcx, [rsi]
0x18006fe38  call    RtlpHpRedirectHeapExport
0x18006fe3d  mov     [rsi], rax
0x18006fe40  mov     eax, ebx
0x18006fe42  mov     rcx, [rbp+47h+var_50]
0x18006fe46  xor     rcx, rsp; StackCookie
0x18006fe49  call    __security_check_cookie
0x18006fe4e  add     rsp, 0F8h
0x18006fe55  pop     r15
0x18006fe57  pop     r14
0x18006fe59  pop     r13
0x18006fe5b  pop     r12
0x18006fe5d  pop     rdi
0x18006fe5e  pop     rsi
0x18006fe5f  pop     rbx
0x18006fe60  pop     rbp
0x18006fe61  retn
0x18006fe63  xor     eax, eax
0x18006fe65  jmp     short loc_18006FE3D
0x18006fe67  test    eax, eax
0x18006fe69  js      short loc_18006FE27
0x18006fe6b  mov     rcx, [rsp+130h+var_F8]
0x18006fe70  test    r15d, r15d
0x18006fe73  jnz     loc_18006FF88
0x18006fe79  mov     rcx, [rcx+30h]
0x18006fe7d  xor     edx, edx
0x18006fe7f  call    RtlGuardCheckImageBase
0x18006fe84  jmp     short loc_18006FE27
0x18006fe86  cmp     r14d, 20h ; ' '
0x18006fe8a  jnb     loc_18006FF46
0x18006fe90  test    r15d, r15d
0x18006fe93  jnz     loc_18006FF46
0x18006fe99  mov     rbx, [rsi]
0x18006fe9c  lea     edx, [r15+2Eh]; Ch
0x18006fea0  mov     rcx, rbx; Str
0x18006fea3  call    strrchr
0x18006fea8  mov     rdi, rax
0x18006feab  test    rax, rax
0x18006feae  jz      loc_18006FF46
0x18006feb4  sub     rax, rbx
0x18006feb7  cmp     rax, 0FFFFh
0x18006febd  ja      loc_18006FF46
0x18006fec3  inc     rdi
0x18006fec6  mov     [rsp+130h+SourceString.Buffer], rbx
0x18006fecb  mov     [rsp+130h+SourceString.Length], ax
0x18006fed0  mov     [rsp+130h+SourceString.MaximumLength], ax
0x18006fed5  cmp     byte ptr [rdi], 23h ; '#'
0x18006fed8  jz      short loc_18006FF32
0x18006feda  mov     r9, [rsp+130h+var_F8]
0x18006fedf  lea     rdx, [rsp+130h+var_D0]
0x18006fee4  mov     r8, r13
0x18006fee7  lea     rcx, [rsp+130h+SourceString]; SourceString
0x18006feec  mov     eax, [r9+110h]
0x18006fef3  mov     [rbp+47h+var_B8], eax
0x18006fef6  lea     rax, [rsp+130h+var_F8]
0x18006fefb  mov     [rsp+130h+var_108], rax; __int64
0x18006ff00  mov     [rsp+130h+var_110], 2; int
0x18006ff08  call    LdrpLoadForwardedDll
0x18006ff0d  mov     ebx, eax
0x18006ff0f  test    eax, eax
0x18006ff11  js      loc_18006FE27
0x18006ff17  mov     rcx, [rsp+130h+var_F8]
0x18006ff1c  call    LdrpDereferenceModule
0x18006ff21  mov     al, [rsp+130h+var_100]
0x18006ff25  inc     r14d
0x18006ff28  mov     rbx, [rsp+130h+var_D8]
0x18006ff2d  jmp     loc_18006FDF9
0x18006ff32  lea     rcx, [rdi+1]; String
0x18006ff36  xor     edx, edx; Base
0x18006ff38  lea     r8, [rsp+130h+Value]; Value
0x18006ff3d  call    RtlCharToInteger
0x18006ff42  test    eax, eax
0x18006ff44  jns     short loc_18006FF50
0x18006ff46  mov     ebx, 0C000007Bh
0x18006ff4b  jmp     loc_18006FE27
0x18006ff50  mov     r12d, [rsp+130h+Value]
0x18006ff55  xor     edi, edi
0x18006ff57  jmp     short loc_18006FEDA
0x18006ff59  test    rdi, rdi
0x18006ff5c  jz      loc_18006FE01
0x18006ff62  mov     rdx, [rsp+130h+var_F8]
0x18006ff67  mov     r8, rdi
0x18006ff6a  mov     rcx, rbx
0x18006ff6d  call    LdrpCheckRedirection
0x18006ff72  cmp     rax, 0FFFFFFFFFFBADD11h
0x18006ff78  jz      loc_18006FE01
0x18006ff7e  mov     [rsi], rax
0x18006ff81  xor     eax, eax
0x18006ff83  jmp     loc_18006FE42
0x18006ff88  mov     rcx, [rcx+0B8h]
0x18006ff8f  mov     dl, 1
0x18006ff91  jmp     loc_18006FE7F
```
