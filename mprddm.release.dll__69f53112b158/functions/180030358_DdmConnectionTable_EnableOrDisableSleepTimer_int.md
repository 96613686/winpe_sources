# DdmConnectionTable::EnableOrDisableSleepTimer(int)

- ea: `0x180030358`
- end: `0x1800304d4`
- name: `?EnableOrDisableSleepTimer@DdmConnectionTable@@AEAAXH@Z`
- size: `380`
- prototype: `void __fastcall(DdmConnectionTable *__hidden this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002fb20`
- `0x1800306c4`

## callees

- `0x180007c0c`
- `0x180030358`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!SetThreadExecutionState` at `0x1800303b8`
- `KERNEL32!SetThreadExecutionState` at `0x180030422`
- `KERNEL32!SetThreadExecutionState` at `0x1800303b8`
- `KERNEL32!SetThreadExecutionState` at `0x180030422`

## string_xrefs

- `0x1800303e1`: `EnableOrDisableSleepTimer: SetThreadExecutionState failed. fDisable=%d`
- `0x180030443`: `EnableOrDisableSleepTimer: SetThreadExecutionState failed. fDisable=%d`

## pseudocode

```c
void __fastcall DdmConnectionTable::EnableOrDisableSleepTimer(DdmConnectionTable *this, unsigned int a2)
{
  __int64 v4; // r8
  __int64 v5; // rax
  _BYTE v6[16]; // [rsp+38h] [rbp-D0h] BYREF
  int *v7; // [rsp+48h] [rbp-C0h]
  int v8; // [rsp+50h] [rbp-B8h]
  int v9; // [rsp+54h] [rbp-B4h]
  int v10; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v11[2044]; // [rsp+5Ch] [rbp-ACh] BYREF

  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( a2 )
  {
    if ( *((_QWORD *)this + 3) == 1 && !SetThreadExecutionState(0x80000001) && (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"EnableOrDisableSleepTimer: SetThreadExecutionState failed. fDisable=%d", a2);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v5 = -1;
        do
          ++v5;
        while ( *(_WORD *)&v11[2 * v5 - 4] );
LABEL_15:
        v9 = 0;
        v8 = 2 * v5 + 2;
        v7 = &v10;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v4, 2, v6);
      }
    }
  }
  else if ( !*((_QWORD *)this + 3) && !SetThreadExecutionState(0x80000000) && (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"EnableOrDisableSleepTimer: SetThreadExecutionState failed. fDisable=%d", 0);
    if ( (byte_1800CF404 & 8) != 0 )
    {
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)&v11[2 * v5 - 4] );
      goto LABEL_15;
    }
  }
}

```

## disassembly

```asm
0x180030358  mov     rax, rsp
0x18003035b  mov     [rax+8], rbx
0x18003035f  mov     [rax+18h], rsi
0x180030363  mov     [rax+20h], rdi
0x180030367  push    rbp
0x180030368  lea     rbp, [rax-768h]
0x18003036f  sub     rsp, 860h
0x180030376  mov     rax, cs:__security_cookie
0x18003037d  xor     rax, rsp
0x180030380  mov     [rbp+760h+var_10], rax
0x180030387  mov     edi, edx
0x180030389  mov     rbx, rcx
0x18003038c  xor     esi, esi
0x18003038e  lea     rcx, [rsp+860h+var_80C]; void *
0x180030393  xor     edx, edx; Val
0x180030395  mov     [rsp+860h+var_810], esi
0x180030399  mov     r8d, 7FCh; Size
0x18003039f  call    memset_0
0x1800303a4  test    edi, edi
0x1800303a6  jz      short loc_180030413
0x1800303a8  cmp     qword ptr [rbx+18h], 1
0x1800303ad  jnz     loc_1800304AB
0x1800303b3  mov     ecx, 80000001h; esFlags
0x1800303b8  call    cs:__imp_SetThreadExecutionState
0x1800303bf  nop     dword ptr [rax+rax+00h]
0x1800303c4  test    eax, eax
0x1800303c6  jnz     loc_1800304AB
0x1800303cc  test    cs:byte_1800CF404, 8
0x1800303d3  jz      loc_1800304AB
0x1800303d9  mov     r8d, edi
0x1800303dc  mov     word ptr [rsp+860h+var_810], si
0x1800303e1  lea     rdx, aEnableordisabl; "EnableOrDisableSleepTimer: SetThreadExe"...
0x1800303e8  lea     rcx, [rsp+860h+var_810]
0x1800303ed  call    FormatRRASErrorString
0x1800303f2  test    cs:byte_1800CF404, 8
0x1800303f9  jz      loc_1800304AB
0x1800303ff  lea     rcx, [rsp+860h+var_810]
0x180030404  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030408  inc     rax
0x18003040b  cmp     [rcx+rax*2], si
0x18003040f  jnz     short loc_180030408
0x180030411  jmp     short loc_18003046F
0x180030413  cmp     [rbx+18h], rsi
0x180030417  jnz     loc_1800304AB
0x18003041d  mov     ecx, 80000000h; esFlags
0x180030422  call    cs:__imp_SetThreadExecutionState
0x180030429  nop     dword ptr [rax+rax+00h]
0x18003042e  test    eax, eax
0x180030430  jnz     short loc_1800304AB
0x180030432  test    cs:byte_1800CF404, 8
0x180030439  jz      short loc_1800304AB
0x18003043b  mov     r8d, edi
0x18003043e  mov     word ptr [rsp+860h+var_810], si
0x180030443  lea     rdx, aEnableordisabl; "EnableOrDisableSleepTimer: SetThreadExe"...
0x18003044a  lea     rcx, [rsp+860h+var_810]
0x18003044f  call    FormatRRASErrorString
0x180030454  test    cs:byte_1800CF404, 8
0x18003045b  jz      short loc_1800304AB
0x18003045d  lea     rcx, [rsp+860h+var_810]
0x180030462  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030466  inc     rax
0x180030469  cmp     [rcx+rax*2], si
0x18003046d  jnz     short loc_180030466
0x18003046f  lea     eax, ds:2[rax*2]
0x180030476  mov     [rsp+860h+var_814], esi
0x18003047a  lea     rcx, [rsp+860h+var_810]
0x18003047f  mov     [rsp+860h+var_818], eax
0x180030483  lea     rax, [rsp+860h+var_830]
0x180030488  mov     [rsp+860h+var_820], rcx
0x18003048d  mov     r9d, 2
0x180030493  mov     [rsp+860h+var_840], rax
0x180030498  lea     rdx, RasDdmTraceError
0x18003049f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800304a6  call    McGenEventWrite_EventWriteTransfer
0x1800304ab  mov     rcx, [rbp+760h+var_10]
0x1800304b2  xor     rcx, rsp; StackCookie
0x1800304b5  call    __security_check_cookie
0x1800304ba  lea     r11, [rsp+860h+var_s0]
0x1800304c2  mov     rbx, [r11+10h]
0x1800304c6  mov     rsi, [r11+20h]
0x1800304ca  mov     rdi, [r11+28h]
0x1800304ce  mov     rsp, r11
0x1800304d1  pop     rbp
0x1800304d2  retn
```
