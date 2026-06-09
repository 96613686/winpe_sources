# CTableManager::GetNext(ulong *)

- ea: `0x180005800`
- end: `0x1800059a8`
- name: `?GetNext@CTableManager@@UEAAJPEAK@Z`
- size: `424`
- prototype: `__int64 __fastcall(CTableManager *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180005800`
- `0x180006400`
- `0x180046494`
- `0x18004a92c`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800058c9`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800058c9`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x18000584d`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x18000584d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTableManager::GetNext(CTableManager *this, unsigned int *a2)
{
  unsigned int v4; // edi
  int ThreadContextRetail; // eax
  CSxGlobalTracer *v6; // rcx
  unsigned int *v7; // rax
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+24h] [rbp-44h]
  __int16 v12; // [rsp+2Ch] [rbp-3Ch]
  const char *v13; // [rsp+30h] [rbp-38h]
  __int128 v14; // [rsp+38h] [rbp-30h] BYREF
  __int64 v15; // [rsp+48h] [rbp-20h]
  int v16; // [rsp+50h] [rbp-18h]

  v10 = 0;
  v11 = 343;
  v4 = 1;
  v12 = 1;
  v13 = "CTableManager::GetNext";
  v14 = 0;
  v15 = 0;
  v16 = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)&v14 + 8);
  if ( ThreadContextRetail >= 0 )
  {
    *(_QWORD *)&v14 = *(_QWORD *)(*((_QWORD *)&v14 + 1) + 32LL);
    *(_QWORD *)(*((_QWORD *)&v14 + 1) + 32LL) = &v10;
LABEL_3:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_4;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
      (unsigned int)ThreadContextRetail);
    goto LABEL_3;
  }
LABEL_4:
  if ( v12 )
  {
    if ( v12 == 1 )
    {
      if ( v6 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v6 + 7) & 0x20000000) == 0 )
        goto LABEL_8;
      v9 = 12;
LABEL_18:
      WPP_SF_s(*((_QWORD *)v6 + 2), v9, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, v13);
      goto LABEL_8;
    }
    if ( v6 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x20000) != 0 )
    {
      v9 = 13;
      goto LABEL_18;
    }
  }
  else if ( v6 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x8000000) != 0 )
  {
    v9 = 11;
    goto LABEL_18;
  }
LABEL_8:
  if ( !a2 )
  {
    v4 = -2147024809;
    WORD1(v11) = 347;
    goto LABEL_14;
  }
  *a2 = 0;
  v10 = 0;
  LOWORD(v11) = 347;
  if ( *((_DWORD *)this + 36) )
  {
    LOWORD(v11) = 353;
LABEL_14:
    v10 = v4;
    goto LABEL_12;
  }
  v7 = (unsigned int *)RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 40), 0);
  if ( v7 )
  {
    *a2 = *v7;
    v4 = v10;
  }
  else
  {
    LOWORD(v11) = 361;
    v10 = 1;
  }
LABEL_12:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return v4;
}

```

## disassembly

```asm
0x180005800  push    rbp
0x180005802  push    rbx
0x180005803  push    rsi
0x180005804  push    rdi
0x180005805  push    r14
0x180005807  push    r15
0x180005809  mov     rbp, rsp
0x18000580c  sub     rsp, 68h
0x180005810  mov     rbx, rdx
0x180005813  mov     rsi, rcx
0x180005816  xor     r14d, r14d
0x180005819  mov     [rbp+var_48], r14d
0x18000581d  mov     [rbp+var_44], 157h
0x180005825  mov     edi, 1
0x18000582a  mov     [rbp+var_3C], di
0x18000582e  lea     rax, aCtablemanagerG_1; "CTableManager::GetNext"
0x180005835  mov     [rbp+var_38], rax
0x180005839  xorps   xmm0, xmm0
0x18000583c  movdqu  [rbp+var_30], xmm0
0x180005841  mov     [rbp+var_20], r14
0x180005845  mov     [rbp+var_18], r14d
0x180005849  lea     rcx, [rbp+var_30+8]
0x18000584d  call    cs:__imp_SxTracerGetThreadContextRetail
0x180005853  lea     r15, WPP_GLOBAL_Control
0x18000585a  test    eax, eax
0x18000585c  js      loc_18000593B
0x180005862  mov     rcx, qword ptr [rbp+var_30+8]
0x180005866  mov     rax, [rcx+20h]
0x18000586a  mov     qword ptr [rbp+var_30], rax
0x18000586e  lea     rax, [rbp+var_48]
0x180005872  mov     [rcx+20h], rax
0x180005876  mov     rcx, cs:WPP_GLOBAL_Control
0x18000587d  movzx   eax, [rbp+var_3C]
0x180005881  test    ax, ax
0x180005884  jz      loc_180005972
0x18000588a  cmp     ax, di
0x18000588d  jnz     short loc_180005901
0x18000588f  cmp     rcx, r15
0x180005892  jz      short loc_1800058A1
0x180005894  test    dword ptr [rcx+1Ch], 20000000h
0x18000589b  jnz     loc_18000598F
0x1800058a1  mov     eax, 15Bh
0x1800058a6  test    rbx, rbx
0x1800058a9  jz      loc_180005999
0x1800058af  mov     [rbx], r14d
0x1800058b2  mov     [rbp+var_48], r14d
0x1800058b6  mov     word ptr [rbp+var_44], ax
0x1800058ba  cmp     dword ptr [rsi+90h], 0
0x1800058c1  jnz     short loc_1800058F3
0x1800058c3  lea     rcx, [rsi+28h]; Table
0x1800058c7  xor     edx, edx; Restart
0x1800058c9  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1800058cf  test    rax, rax
0x1800058d2  jz      short loc_18000592D
0x1800058d4  mov     eax, [rax]
0x1800058d6  mov     [rbx], eax
0x1800058d8  mov     edi, [rbp+var_48]
0x1800058db  lea     rcx, [rbp+var_48]; this
0x1800058df  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800058e4  mov     eax, edi
0x1800058e6  add     rsp, 68h
0x1800058ea  pop     r15
0x1800058ec  pop     r14
0x1800058ee  pop     rdi
0x1800058ef  pop     rsi
0x1800058f0  pop     rbx
0x1800058f1  pop     rbp
0x1800058f2  retn
0x1800058f3  mov     eax, 161h
0x1800058f8  mov     word ptr [rbp+var_44], ax
0x1800058fc  mov     [rbp+var_48], edi
0x1800058ff  jmp     short loc_1800058DB
0x180005901  cmp     rcx, r15
0x180005904  jz      short loc_1800058A1
0x180005906  test    dword ptr [rcx+1Ch], 20000h
0x18000590d  jz      short loc_1800058A1
0x18000590f  mov     edx, 0Dh
0x180005914  mov     r9, [rbp+var_38]
0x180005918  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x18000591f  mov     rcx, [rcx+10h]
0x180005923  call    WPP_SF_s
0x180005928  jmp     loc_1800058A1
0x18000592d  mov     eax, 169h
0x180005932  mov     word ptr [rbp+var_44], ax
0x180005936  mov     [rbp+var_48], edi
0x180005939  jmp     short loc_1800058DB
0x18000593b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005942  cmp     rcx, r15
0x180005945  jz      loc_18000587D
0x18000594b  test    [rcx+1Ch], dil
0x18000594f  jz      loc_18000587D
0x180005955  mov     edx, 0Ah
0x18000595a  mov     r9d, eax
0x18000595d  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x180005964  mov     rcx, [rcx+10h]
0x180005968  call    WPP_SF_d
0x18000596d  jmp     loc_180005876
0x180005972  cmp     rcx, r15
0x180005975  jz      loc_1800058A1
0x18000597b  test    dword ptr [rcx+1Ch], 8000000h
0x180005982  jz      loc_1800058A1
0x180005988  mov     edx, 0Bh
0x18000598d  jmp     short loc_180005914
0x18000598f  mov     edx, 0Ch
0x180005994  jmp     loc_180005914
0x180005999  mov     edi, 80070057h
0x18000599e  mov     word ptr [rbp+var_44+2], ax
0x1800059a2  jmp     loc_1800058FC
```
