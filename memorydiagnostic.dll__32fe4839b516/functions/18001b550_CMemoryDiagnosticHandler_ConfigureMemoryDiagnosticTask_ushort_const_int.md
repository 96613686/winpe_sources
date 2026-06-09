# CMemoryDiagnosticHandler::ConfigureMemoryDiagnosticTask(ushort const *,int)

- ea: `0x18001b550`
- end: `0x18001b852`
- name: `?ConfigureMemoryDiagnosticTask@CMemoryDiagnosticHandler@@AEAAJPEBGH@Z`
- size: `770`
- prototype: `__int64 __fastcall(CMemoryDiagnosticHandler *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d530`
- `0x18001ead0`

## callees

- `0x18001b550`
- `0x18001f560`
- `0x18001f594`
- `0x180024010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18001b64d`
- `ole32!CoCreateInstance` at `0x18001b64d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b5b7`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b5f5`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b5b7`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b5f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b7ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b7fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b7ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b7fe`
- `OLEAUT32!__imp_VariantInit` at `0x18001b58e`
- `OLEAUT32!__imp_VariantInit` at `0x18001b58e`
- `OLEAUT32!__imp_VariantClear` at `0x18001b80e`
- `OLEAUT32!__imp_VariantClear` at `0x18001b80e`

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
  v19 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v3 = 0;
  v4 = 0;
  VariantInit(&pvarg);
  if ( !a2 )
  {
    v5 = -2147024809;
    goto LABEL_32;
  }
  v3 = SysAllocString(L"\\Microsoft\\Windows\\MemoryDiagnostic");
  if ( v3 )
  {
    v4 = SysAllocString(a2);
    if ( v4 )
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
          v5 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v3, &v20);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v20 + 104LL))(v20, v4, &v19);
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
  if ( v3 )
    SysFreeString(v3);
  if ( v4 )
    SysFreeString(v4);
  VariantClear(&pvarg);
  if ( v5 < 0
    && WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v10, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001b550  mov     [rsp-8+arg_0], rcx
0x18001b555  push    rbp
0x18001b556  push    rbx
0x18001b557  push    rsi
0x18001b558  push    rdi
0x18001b559  push    r12
0x18001b55b  lea     rbp, [rsp-37h]
0x18001b560  sub     rsp, 0D0h
0x18001b567  and     [rbp+57h+arg_0], 0
0x18001b56c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001b570  and     [rbp+57h+arg_18], 0
0x18001b575  xorps   xmm0, xmm0
0x18001b578  and     [rbp+57h+arg_8], 0
0x18001b57d  xor     eax, eax
0x18001b57f  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001b583  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001b587  mov     rbx, rdx
0x18001b58a  xor     esi, esi
0x18001b58c  xor     edi, edi
0x18001b58e  call    cs:__imp_VariantInit
0x18001b595  nop     dword ptr [rax+rax+00h]
0x18001b59a  lea     r12, WPP_GLOBAL_Control
0x18001b5a1  test    rbx, rbx
0x18001b5a4  jnz     short loc_18001B5B0
0x18001b5a6  mov     ebx, 80070057h
0x18001b5ab  jmp     loc_18001B7A3
0x18001b5b0  lea     rcx, psz; "\\Microsoft\\Windows\\MemoryDiagnostic"
0x18001b5b7  call    cs:__imp_SysAllocString
0x18001b5be  nop     dword ptr [rax+rax+00h]
0x18001b5c3  mov     rsi, rax
0x18001b5c6  test    rax, rax
0x18001b5c9  jnz     short loc_18001B5F2
0x18001b5cb  mov     ebx, 8007000Eh
0x18001b5d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5d7  cmp     rcx, r12
0x18001b5da  jz      loc_18001B7A3
0x18001b5e0  test    byte ptr [rcx+1Ch], 1
0x18001b5e4  jz      loc_18001B7A3
0x18001b5ea  lea     edx, [rax+0Eh]
0x18001b5ed  jmp     loc_18001B79A
0x18001b5f2  mov     rcx, rbx; psz
0x18001b5f5  call    cs:__imp_SysAllocString
0x18001b5fc  nop     dword ptr [rax+rax+00h]
0x18001b601  mov     rdi, rax
0x18001b604  test    rax, rax
0x18001b607  jnz     short loc_18001B630
0x18001b609  mov     ebx, 8007000Eh
0x18001b60e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b615  cmp     rcx, r12
0x18001b618  jz      loc_18001B7A3
0x18001b61e  test    byte ptr [rcx+1Ch], 1
0x18001b622  jz      loc_18001B7A3
0x18001b628  lea     edx, [rax+0Fh]
0x18001b62b  jmp     loc_18001B79A
0x18001b630  xor     edx, edx; pUnkOuter
0x18001b632  lea     rax, [rbp+57h+arg_0]
0x18001b636  lea     r9, IID_ITaskService; riid
0x18001b63d  mov     [rsp+0F0h+ppv], rax; ppv
0x18001b642  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001b649  lea     r8d, [rdx+1]; dwClsContext
0x18001b64d  call    cs:__imp_CoCreateInstance
0x18001b654  nop     dword ptr [rax+rax+00h]
0x18001b659  mov     ebx, eax
0x18001b65b  test    eax, eax
0x18001b65d  jns     short loc_18001B683
0x18001b65f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b666  cmp     rcx, r12
0x18001b669  jz      loc_18001B7A3
0x18001b66f  test    byte ptr [rcx+1Ch], 1
0x18001b673  jz      loc_18001B7A3
0x18001b679  mov     edx, 10h
0x18001b67e  jmp     loc_18001B79A
0x18001b683  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18001b687  lea     rdx, [rbp+57h+var_A0]
0x18001b68b  mov     rcx, [rbp+57h+arg_0]
0x18001b68f  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18001b694  lea     r9, [rbp+57h+var_80]
0x18001b698  mov     [rsp+0F0h+ppv], rdx
0x18001b69d  lea     r8, [rbp+57h+var_60]
0x18001b6a1  lea     rdx, [rbp+57h+var_40]
0x18001b6a5  movaps  [rbp+57h+var_A0], xmm1
0x18001b6a9  mov     rax, [rcx]
0x18001b6ac  movsd   [rbp+57h+var_90], xmm0
0x18001b6b1  movaps  [rbp+57h+var_80], xmm1
0x18001b6b5  movsd   [rbp+57h+var_70], xmm0
0x18001b6ba  mov     rax, [rax+50h]
0x18001b6be  movaps  [rbp+57h+var_60], xmm1
0x18001b6c2  movsd   [rbp+57h+var_50], xmm0
0x18001b6c7  movaps  [rbp+57h+var_40], xmm1
0x18001b6cb  movsd   [rbp+57h+var_30], xmm0
0x18001b6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6d5  mov     ebx, eax
0x18001b6d7  test    eax, eax
0x18001b6d9  jns     short loc_18001B6FF
0x18001b6db  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6e2  cmp     rcx, r12
0x18001b6e5  jz      loc_18001B7A3
0x18001b6eb  test    byte ptr [rcx+1Ch], 1
0x18001b6ef  jz      loc_18001B7A3
0x18001b6f5  mov     edx, 11h
0x18001b6fa  jmp     loc_18001B79A
0x18001b6ff  mov     rcx, [rbp+57h+arg_0]
0x18001b703  lea     r8, [rbp+57h+arg_18]
0x18001b707  mov     rdx, rsi
0x18001b70a  mov     rax, [rcx]
0x18001b70d  mov     rax, [rax+38h]
0x18001b711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b716  mov     ebx, eax
0x18001b718  test    eax, eax
0x18001b71a  jns     short loc_18001B735
0x18001b71c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b723  cmp     rcx, r12
0x18001b726  jz      short loc_18001B7A3
0x18001b728  test    byte ptr [rcx+1Ch], 1
0x18001b72c  jz      short loc_18001B7A3
0x18001b72e  mov     edx, 12h
0x18001b733  jmp     short loc_18001B79A
0x18001b735  mov     rcx, [rbp+57h+arg_18]
0x18001b739  lea     r8, [rbp+57h+arg_8]
0x18001b73d  mov     rdx, rdi
0x18001b740  mov     rax, [rcx]
0x18001b743  mov     rax, [rax+68h]
0x18001b747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b74c  mov     ebx, eax
0x18001b74e  test    eax, eax
0x18001b750  jns     short loc_18001B76B
0x18001b752  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b759  cmp     rcx, r12
0x18001b75c  jz      short loc_18001B7A3
0x18001b75e  test    byte ptr [rcx+1Ch], 1
0x18001b762  jz      short loc_18001B7A3
0x18001b764  mov     edx, 13h
0x18001b769  jmp     short loc_18001B79A
0x18001b76b  mov     rcx, [rbp+57h+arg_8]
0x18001b76f  xor     edx, edx
0x18001b771  mov     rax, [rcx]
0x18001b774  mov     rax, [rax+58h]
0x18001b778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b77d  mov     ebx, eax
0x18001b77f  test    eax, eax
0x18001b781  jns     short loc_18001B7A3
0x18001b783  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b78a  cmp     rcx, r12
0x18001b78d  jz      short loc_18001B7A3
0x18001b78f  test    byte ptr [rcx+1Ch], 1
0x18001b793  jz      short loc_18001B7A3
0x18001b795  mov     edx, 14h
0x18001b79a  mov     rcx, [rcx+10h]
0x18001b79e  call    WPP_SF_
0x18001b7a3  mov     rcx, [rbp+57h+arg_8]
0x18001b7a7  test    rcx, rcx
0x18001b7aa  jz      short loc_18001B7B8
0x18001b7ac  mov     rax, [rcx]
0x18001b7af  mov     rax, [rax+10h]
0x18001b7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7b8  mov     rcx, [rbp+57h+arg_18]
0x18001b7bc  test    rcx, rcx
0x18001b7bf  jz      short loc_18001B7CD
0x18001b7c1  mov     rax, [rcx]
0x18001b7c4  mov     rax, [rax+10h]
0x18001b7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7cd  mov     rcx, [rbp+57h+arg_0]
0x18001b7d1  test    rcx, rcx
0x18001b7d4  jz      short loc_18001B7E2
0x18001b7d6  mov     rax, [rcx]
0x18001b7d9  mov     rax, [rax+10h]
0x18001b7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7e2  test    rsi, rsi
0x18001b7e5  jz      short loc_18001B7F6
0x18001b7e7  mov     rcx, rsi; bstrString
0x18001b7ea  call    cs:__imp_SysFreeString
0x18001b7f1  nop     dword ptr [rax+rax+00h]
0x18001b7f6  test    rdi, rdi
0x18001b7f9  jz      short loc_18001B80A
0x18001b7fb  mov     rcx, rdi; bstrString
0x18001b7fe  call    cs:__imp_SysFreeString
0x18001b805  nop     dword ptr [rax+rax+00h]
0x18001b80a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001b80e  call    cs:__imp_VariantClear
0x18001b815  nop     dword ptr [rax+rax+00h]
0x18001b81a  test    ebx, ebx
0x18001b81c  jns     short loc_18001B841
0x18001b81e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b825  cmp     rcx, r12
0x18001b828  jz      short loc_18001B841
0x18001b82a  test    byte ptr [rcx+1Ch], 1
0x18001b82e  jz      short loc_18001B841
0x18001b830  mov     rcx, [rcx+10h]
0x18001b834  mov     edx, 0Ah
0x18001b839  mov     r9d, ebx
0x18001b83c  call    WPP_SF_D
0x18001b841  mov     eax, ebx
0x18001b843  add     rsp, 0D0h
0x18001b84a  pop     r12
0x18001b84c  pop     rdi
0x18001b84d  pop     rsi
0x18001b84e  pop     rbx
0x18001b84f  pop     rbp
0x18001b850  retn
```
