# CFileOperation::SetFile(_CFile *,ulong)

- ea: `0x1800059b0`
- end: `0x180005b63`
- name: `?SetFile@CFileOperation@@UEAAJPEAU_CFile@@K@Z`
- size: `435`
- prototype: `__int64 __fastcall(CFileOperation *__hidden this, struct _CFile *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x1800059b0`
- `0x180006400`
- `0x180038c3c`
- `0x180046494`
- `0x18004a92c`

## import_xrefs

- `SXSHARED!SxTracerGetThreadContextRetail` at `0x180005a20`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x180005a20`

## string_xrefs

- `0x180005a01`: `CFileOperation::SetFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileOperation::SetFile(CFileOperation *this, struct _CFile *a2, int a3)
{
  int ThreadContextRetail; // eax
  CSxGlobalTracer *v7; // rcx
  __int16 v8; // ax
  unsigned int v9; // ebx
  __int64 v11; // rdx
  unsigned int v12; // [rsp+20h] [rbp-48h] BYREF
  __int64 v13; // [rsp+24h] [rbp-44h]
  __int16 v14; // [rsp+2Ch] [rbp-3Ch]
  const char *v15; // [rsp+30h] [rbp-38h]
  __int128 v16; // [rsp+38h] [rbp-30h] BYREF
  __int64 v17; // [rsp+48h] [rbp-20h]
  int v18; // [rsp+50h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_7d91fd3008b83281181ea730215a620a_Traceguids);
  }
  v12 = 0;
  v13 = 550;
  v14 = 1;
  v15 = "CFileOperation::SetFile";
  v16 = 0;
  v17 = 0;
  v18 = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)&v16 + 8);
  if ( ThreadContextRetail >= 0 )
  {
    *(_QWORD *)&v16 = *(_QWORD *)(*((_QWORD *)&v16 + 1) + 32LL);
    *(_QWORD *)(*((_QWORD *)&v16 + 1) + 32LL) = &v12;
LABEL_6:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
      (unsigned int)ThreadContextRetail);
    goto LABEL_6;
  }
LABEL_7:
  if ( v14 )
  {
    if ( v14 == 1 )
    {
      if ( v7 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v7 + 7) & 0x20000000) == 0 )
        goto LABEL_11;
      v11 = 12;
LABEL_19:
      WPP_SF_s(*((_QWORD *)v7 + 2), v11, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, v15);
      goto LABEL_11;
    }
    if ( v7 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x20000) != 0 )
    {
      v11 = 13;
      goto LABEL_19;
    }
  }
  else if ( v7 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x8000000) != 0 )
  {
    v11 = 11;
    goto LABEL_19;
  }
LABEL_11:
  v8 = 552;
  if ( a2 && (LOWORD(v13) = 552, v8 = 553, a3) )
  {
    v9 = 0;
    LOWORD(v13) = 553;
    *((_QWORD *)this + 6) = a2;
    *((_DWORD *)this + 14) = 0;
    *((_DWORD *)this + 15) = a3;
  }
  else
  {
    v9 = -2147024809;
    WORD1(v13) = v8;
  }
  v12 = v9;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return v9;
}

```

## disassembly

```asm
0x1800059b0  push    rbp
0x1800059b2  push    rbx
0x1800059b3  push    rsi
0x1800059b4  push    rdi
0x1800059b5  push    r14
0x1800059b7  push    r15
0x1800059b9  mov     rbp, rsp
0x1800059bc  sub     rsp, 68h
0x1800059c0  mov     r14d, r8d
0x1800059c3  mov     rsi, rdx
0x1800059c6  mov     rdi, rcx
0x1800059c9  lea     rbx, WPP_GLOBAL_Control
0x1800059d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059d7  cmp     rcx, rbx
0x1800059da  jz      short loc_1800059E9
0x1800059dc  test    dword ptr [rcx+1Ch], 20000000h
0x1800059e3  jnz     loc_180005AE8
0x1800059e9  xor     r15d, r15d
0x1800059ec  mov     [rbp+var_48], r15d
0x1800059f0  mov     [rbp+var_44], 226h
0x1800059f8  mov     eax, 1
0x1800059fd  mov     [rbp+var_3C], ax
0x180005a01  lea     rax, aCfileoperation_25; "CFileOperation::SetFile"
0x180005a08  mov     [rbp+var_38], rax
0x180005a0c  xorps   xmm0, xmm0
0x180005a0f  movdqu  [rbp+var_30], xmm0
0x180005a14  mov     [rbp+var_20], r15
0x180005a18  mov     [rbp+var_18], r15d
0x180005a1c  lea     rcx, [rbp+var_30+8]
0x180005a20  call    cs:__imp_SxTracerGetThreadContextRetail
0x180005a26  test    eax, eax
0x180005a28  js      loc_180005B02
0x180005a2e  mov     rcx, qword ptr [rbp+var_30+8]
0x180005a32  mov     rax, [rcx+20h]
0x180005a36  mov     qword ptr [rbp+var_30], rax
0x180005a3a  lea     rax, [rbp+var_48]
0x180005a3e  mov     [rcx+20h], rax
0x180005a42  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a49  movzx   eax, [rbp+var_3C]
0x180005a4d  test    ax, ax
0x180005a50  jz      loc_180005B39
0x180005a56  cmp     ax, 1
0x180005a5a  jnz     short loc_180005ABF
0x180005a5c  cmp     rcx, rbx
0x180005a5f  jz      short loc_180005A6E
0x180005a61  test    dword ptr [rcx+1Ch], 20000000h
0x180005a68  jnz     loc_180005B59
0x180005a6e  mov     eax, 228h
0x180005a73  test    rsi, rsi
0x180005a76  jnz     short loc_180005A9C
0x180005a78  mov     ebx, 80070057h
0x180005a7d  mov     word ptr [rbp+var_44+2], ax
0x180005a81  mov     [rbp+var_48], ebx
0x180005a84  lea     rcx, [rbp+var_48]; this
0x180005a88  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180005a8d  mov     eax, ebx
0x180005a8f  add     rsp, 68h
0x180005a93  pop     r15
0x180005a95  pop     r14
0x180005a97  pop     rdi
0x180005a98  pop     rsi
0x180005a99  pop     rbx
0x180005a9a  pop     rbp
0x180005a9b  retn
0x180005a9c  mov     word ptr [rbp+var_44], ax
0x180005aa0  mov     eax, 229h
0x180005aa5  test    r14d, r14d
0x180005aa8  jz      short loc_180005A78
0x180005aaa  mov     ebx, r15d
0x180005aad  mov     word ptr [rbp+var_44], ax
0x180005ab1  mov     [rdi+30h], rsi
0x180005ab5  mov     [rdi+38h], r15d
0x180005ab9  mov     [rdi+3Ch], r14d
0x180005abd  jmp     short loc_180005A81
0x180005abf  cmp     rcx, rbx
0x180005ac2  jz      short loc_180005A6E
0x180005ac4  test    dword ptr [rcx+1Ch], 20000h
0x180005acb  jz      short loc_180005A6E
0x180005acd  mov     edx, 0Dh
0x180005ad2  mov     r9, [rbp+var_38]
0x180005ad6  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x180005add  mov     rcx, [rcx+10h]
0x180005ae1  call    WPP_SF_s
0x180005ae6  jmp     short loc_180005A6E
0x180005ae8  mov     edx, 14h
0x180005aed  lea     r8, WPP_7d91fd3008b83281181ea730215a620a_Traceguids
0x180005af4  mov     rcx, [rcx+10h]
0x180005af8  call    WPP_SF_
0x180005afd  jmp     loc_1800059E9
0x180005b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b09  cmp     rcx, rbx
0x180005b0c  jz      loc_180005A49
0x180005b12  test    byte ptr [rcx+1Ch], 1
0x180005b16  jz      loc_180005A49
0x180005b1c  mov     edx, 0Ah
0x180005b21  mov     r9d, eax
0x180005b24  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x180005b2b  mov     rcx, [rcx+10h]
0x180005b2f  call    WPP_SF_d
0x180005b34  jmp     loc_180005A42
0x180005b39  cmp     rcx, rbx
0x180005b3c  jz      loc_180005A6E
0x180005b42  test    dword ptr [rcx+1Ch], 8000000h
0x180005b49  jz      loc_180005A6E
0x180005b4f  mov     edx, 0Bh
0x180005b54  jmp     loc_180005AD2
0x180005b59  mov     edx, 0Ch
0x180005b5e  jmp     loc_180005AD2
```
