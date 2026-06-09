# CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(ushort const *,int)

- ea: `0x18001a5a0`
- end: `0x18001a880`
- name: `?ConfigureMemoryDiagnosticTask@CMemoryDiagnosticHandler@@AEAAJPEBGH@Z`
- size: `736`
- prototype: `__int64 __fastcall(CMemoryDiagnosticHandler *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c310`
- `0x18001d7a0`

## callees

- `0x18001a5a0`
- `0x18001e21c`
- `0x18001e24c`
- `0x180023010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18001a694`
- `ole32!CoCreateInstance` at `0x18001a694`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a60a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a642`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a60a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a642`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a82b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a839`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a82b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a839`
- `OLEAUT32!__imp_VariantInit` at `0x18001a5e5`
- `OLEAUT32!__imp_VariantInit` at `0x18001a5e5`
- `OLEAUT32!__imp_VariantClear` at `0x18001a843`
- `OLEAUT32!__imp_VariantClear` at `0x18001a843`

## pseudocode

```c
__int64 __fastcall CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(
        CMemoryDiagnosticHandler *this,
        const unsigned __int16 *a2)
{
  OLECHAR *v3; // rsi
  OLECHAR *v4; // rdi
  HRESULT v5; // ebx
  CMemoryDiagnosticHandler *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 (__fastcall *v9)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  __int64 v10; // r8
  VARIANTARG pvarg; // [rsp+30h] [rbp-69h] BYREF
  __int128 v13; // [rsp+50h] [rbp-49h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-39h]
  VARIANTARG v15; // [rsp+70h] [rbp-29h] BYREF
  VARIANTARG v16; // [rsp+90h] [rbp-9h] BYREF
  VARIANTARG v17; // [rsp+B0h] [rbp+17h] BYREF
  LPVOID ppv; // [rsp+100h] [rbp+67h] BYREF
  __int64 v19; // [rsp+108h] [rbp+6Fh] BYREF
  __int64 v20; // [rsp+118h] [rbp+7Fh] BYREF

  ppv = 0;
  v20 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v19 = 0;
  v3 = 0;
  VariantInit(&pvarg);
  if ( !a2 )
  {
    v4 = 0;
    v5 = -2147024809;
    goto LABEL_32;
  }
  v4 = SysAllocString(L"\\Microsoft\\Windows\\MemoryDiagnostic");
  if ( v4 )
  {
    v3 = SysAllocString(a2);
    if ( v3 )
    {
      v5 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
      if ( v5 >= 0 )
      {
        v13 = *(_OWORD *)&pvarg.vt;
        v8 = *(_QWORD *)ppv;
        pRecInfo = pvarg.pRecInfo;
        v15 = pvarg;
        v9 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v8 + 80);
        v16 = pvarg;
        v17 = pvarg;
        v5 = v9(ppv, &v17, &v16, &v15, &v13);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v4, &v20);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v20 + 104LL))(v20, v3, &v19);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 88LL))(v19, 0);
              if ( v5 < 0 )
              {
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v7 = 20;
                  goto LABEL_31;
                }
              }
            }
            else
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v7 = 19;
                goto LABEL_31;
              }
            }
          }
          else
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v7 = 18;
              goto LABEL_31;
            }
          }
        }
        else
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v7 = 17;
            goto LABEL_31;
          }
        }
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 16;
          goto LABEL_31;
        }
      }
    }
    else
    {
      v5 = -2147024882;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 15;
        goto LABEL_31;
      }
    }
  }
  else
  {
    v5 = -2147024882;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 14;
LABEL_31:
      WPP_SF_(*((_QWORD *)v6 + 2), v7);
    }
  }
LABEL_32:
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v4 )
    SysFreeString(v4);
  if ( v3 )
    SysFreeString(v3);
  VariantClear(&pvarg);
  if ( v5 < 0
    && WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v10, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001a5a0  mov     [rsp-8+arg_0], rcx
0x18001a5a5  push    rbp
0x18001a5a6  push    rbx
0x18001a5a7  push    rsi
0x18001a5a8  push    rdi
0x18001a5a9  push    r12
0x18001a5ab  lea     rbp, [rsp-37h]
0x18001a5b0  sub     rsp, 0D0h
0x18001a5b7  xorps   xmm0, xmm0
0x18001a5ba  mov     [rbp+57h+arg_0], 0
0x18001a5c2  xor     eax, eax
0x18001a5c4  mov     [rbp+57h+arg_18], 0
0x18001a5cc  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001a5d0  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001a5d4  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001a5d8  mov     rbx, rdx
0x18001a5db  mov     [rbp+57h+arg_8], 0
0x18001a5e3  xor     esi, esi
0x18001a5e5  call    cs:__imp_VariantInit
0x18001a5eb  lea     r12, WPP_GLOBAL_Control
0x18001a5f2  test    rbx, rbx
0x18001a5f5  jnz     short loc_18001A603
0x18001a5f7  xor     edi, edi
0x18001a5f9  mov     ebx, 80070057h
0x18001a5fe  jmp     loc_18001A7E4
0x18001a603  lea     rcx, psz; "\\Microsoft\\Windows\\MemoryDiagnostic"
0x18001a60a  call    cs:__imp_SysAllocString
0x18001a610  mov     rdi, rax
0x18001a613  test    rax, rax
0x18001a616  jnz     short loc_18001A63F
0x18001a618  mov     ebx, 8007000Eh
0x18001a61d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a624  cmp     rcx, r12
0x18001a627  jz      loc_18001A7E4
0x18001a62d  test    byte ptr [rcx+1Ch], 1
0x18001a631  jz      loc_18001A7E4
0x18001a637  lea     edx, [rax+0Eh]
0x18001a63a  jmp     loc_18001A7DB
0x18001a63f  mov     rcx, rbx; psz
0x18001a642  call    cs:__imp_SysAllocString
0x18001a648  mov     rsi, rax
0x18001a64b  test    rax, rax
0x18001a64e  jnz     short loc_18001A677
0x18001a650  mov     ebx, 8007000Eh
0x18001a655  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a65c  cmp     rcx, r12
0x18001a65f  jz      loc_18001A7E4
0x18001a665  test    byte ptr [rcx+1Ch], 1
0x18001a669  jz      loc_18001A7E4
0x18001a66f  lea     edx, [rax+0Fh]
0x18001a672  jmp     loc_18001A7DB
0x18001a677  xor     edx, edx; pUnkOuter
0x18001a679  lea     rax, [rbp+57h+arg_0]
0x18001a67d  lea     r9, IID_ITaskService; riid
0x18001a684  mov     [rsp+0F0h+ppv], rax; ppv
0x18001a689  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001a690  lea     r8d, [rdx+1]; dwClsContext
0x18001a694  call    cs:__imp_CoCreateInstance
0x18001a69a  mov     ebx, eax
0x18001a69c  test    eax, eax
0x18001a69e  jns     short loc_18001A6C4
0x18001a6a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6a7  cmp     rcx, r12
0x18001a6aa  jz      loc_18001A7E4
0x18001a6b0  test    byte ptr [rcx+1Ch], 1
0x18001a6b4  jz      loc_18001A7E4
0x18001a6ba  mov     edx, 10h
0x18001a6bf  jmp     loc_18001A7DB
0x18001a6c4  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18001a6c8  lea     rdx, [rbp+57h+var_A0]
0x18001a6cc  mov     rcx, [rbp+57h+arg_0]
0x18001a6d0  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18001a6d5  lea     r9, [rbp+57h+var_80]
0x18001a6d9  mov     [rsp+0F0h+ppv], rdx
0x18001a6de  lea     r8, [rbp+57h+var_60]
0x18001a6e2  lea     rdx, [rbp+57h+var_40]
0x18001a6e6  movaps  [rbp+57h+var_A0], xmm1
0x18001a6ea  mov     rax, [rcx]
0x18001a6ed  movsd   [rbp+57h+var_90], xmm0
0x18001a6f2  movaps  [rbp+57h+var_80], xmm1
0x18001a6f6  movsd   [rbp+57h+var_70], xmm0
0x18001a6fb  mov     rax, [rax+50h]
0x18001a6ff  movaps  [rbp+57h+var_60], xmm1
0x18001a703  movsd   [rbp+57h+var_50], xmm0
0x18001a708  movaps  [rbp+57h+var_40], xmm1
0x18001a70c  movsd   [rbp+57h+var_30], xmm0
0x18001a711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a716  mov     ebx, eax
0x18001a718  test    eax, eax
0x18001a71a  jns     short loc_18001A740
0x18001a71c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a723  cmp     rcx, r12
0x18001a726  jz      loc_18001A7E4
0x18001a72c  test    byte ptr [rcx+1Ch], 1
0x18001a730  jz      loc_18001A7E4
0x18001a736  mov     edx, 11h
0x18001a73b  jmp     loc_18001A7DB
0x18001a740  mov     rcx, [rbp+57h+arg_0]
0x18001a744  lea     r8, [rbp+57h+arg_18]
0x18001a748  mov     rdx, rdi
0x18001a74b  mov     rax, [rcx]
0x18001a74e  mov     rax, [rax+38h]
0x18001a752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a757  mov     ebx, eax
0x18001a759  test    eax, eax
0x18001a75b  jns     short loc_18001A776
0x18001a75d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a764  cmp     rcx, r12
0x18001a767  jz      short loc_18001A7E4
0x18001a769  test    byte ptr [rcx+1Ch], 1
0x18001a76d  jz      short loc_18001A7E4
0x18001a76f  mov     edx, 12h
0x18001a774  jmp     short loc_18001A7DB
0x18001a776  mov     rcx, [rbp+57h+arg_18]
0x18001a77a  lea     r8, [rbp+57h+arg_8]
0x18001a77e  mov     rdx, rsi
0x18001a781  mov     rax, [rcx]
0x18001a784  mov     rax, [rax+68h]
0x18001a788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a78d  mov     ebx, eax
0x18001a78f  test    eax, eax
0x18001a791  jns     short loc_18001A7AC
0x18001a793  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a79a  cmp     rcx, r12
0x18001a79d  jz      short loc_18001A7E4
0x18001a79f  test    byte ptr [rcx+1Ch], 1
0x18001a7a3  jz      short loc_18001A7E4
0x18001a7a5  mov     edx, 13h
0x18001a7aa  jmp     short loc_18001A7DB
0x18001a7ac  mov     rcx, [rbp+57h+arg_8]
0x18001a7b0  xor     edx, edx
0x18001a7b2  mov     rax, [rcx]
0x18001a7b5  mov     rax, [rax+58h]
0x18001a7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7be  mov     ebx, eax
0x18001a7c0  test    eax, eax
0x18001a7c2  jns     short loc_18001A7E4
0x18001a7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7cb  cmp     rcx, r12
0x18001a7ce  jz      short loc_18001A7E4
0x18001a7d0  test    byte ptr [rcx+1Ch], 1
0x18001a7d4  jz      short loc_18001A7E4
0x18001a7d6  mov     edx, 14h
0x18001a7db  mov     rcx, [rcx+10h]
0x18001a7df  call    WPP_SF_
0x18001a7e4  mov     rcx, [rbp+57h+arg_8]
0x18001a7e8  test    rcx, rcx
0x18001a7eb  jz      short loc_18001A7F9
0x18001a7ed  mov     rax, [rcx]
0x18001a7f0  mov     rax, [rax+10h]
0x18001a7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7f9  mov     rcx, [rbp+57h+arg_18]
0x18001a7fd  test    rcx, rcx
0x18001a800  jz      short loc_18001A80E
0x18001a802  mov     rax, [rcx]
0x18001a805  mov     rax, [rax+10h]
0x18001a809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a80e  mov     rcx, [rbp+57h+arg_0]
0x18001a812  test    rcx, rcx
0x18001a815  jz      short loc_18001A823
0x18001a817  mov     rax, [rcx]
0x18001a81a  mov     rax, [rax+10h]
0x18001a81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a823  test    rdi, rdi
0x18001a826  jz      short loc_18001A831
0x18001a828  mov     rcx, rdi; bstrString
0x18001a82b  call    cs:__imp_SysFreeString
0x18001a831  test    rsi, rsi
0x18001a834  jz      short loc_18001A83F
0x18001a836  mov     rcx, rsi; bstrString
0x18001a839  call    cs:__imp_SysFreeString
0x18001a83f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001a843  call    cs:__imp_VariantClear
0x18001a849  test    ebx, ebx
0x18001a84b  jns     short loc_18001A870
0x18001a84d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a854  cmp     rcx, r12
0x18001a857  jz      short loc_18001A870
0x18001a859  test    byte ptr [rcx+1Ch], 1
0x18001a85d  jz      short loc_18001A870
0x18001a85f  mov     rcx, [rcx+10h]
0x18001a863  mov     edx, 0Ah
0x18001a868  mov     r9d, ebx
0x18001a86b  call    WPP_SF_d
0x18001a870  mov     eax, ebx
0x18001a872  add     rsp, 0D0h
0x18001a879  pop     r12
0x18001a87b  pop     rdi
0x18001a87c  pop     rsi
0x18001a87d  pop     rbx
0x18001a87e  pop     rbp
0x18001a87f  retn
```
