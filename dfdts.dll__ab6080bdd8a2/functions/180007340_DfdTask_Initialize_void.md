# DfdTask::Initialize(void)

- ea: `0x180007340`
- end: `0x1800075c7`
- name: `?Initialize@DfdTask@@QEAAJXZ`
- size: `647`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000357c`

## callees

- `0x180002c90`
- `0x180007340`
- `0x180009010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007376`
- `OLEAUT32!__imp_SysAllocString` at `0x180007386`
- `OLEAUT32!__imp_SysAllocString` at `0x180007376`
- `OLEAUT32!__imp_SysAllocString` at `0x180007386`
- `OLEAUT32!__imp_SysFreeString` at `0x180007597`
- `OLEAUT32!__imp_SysFreeString` at `0x1800075a5`
- `OLEAUT32!__imp_SysFreeString` at `0x180007597`
- `OLEAUT32!__imp_SysFreeString` at `0x1800075a5`
- `OLEAUT32!__imp_VariantInit` at `0x180007369`
- `OLEAUT32!__imp_VariantInit` at `0x180007369`
- `OLEAUT32!__imp_VariantClear` at `0x1800075af`
- `OLEAUT32!__imp_VariantClear` at `0x1800075af`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800073ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800073ba`

## pseudocode

```c
__int64 __fastcall DfdTask::Initialize(LPVOID *ppv)
{
  OLECHAR *v2; // r14
  BSTR v3; // rax
  OLECHAR *v4; // rsi
  HRESULT Instance; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 *v10; // rcx
  __int64 v11; // rax
  __int64 (__fastcall *v12)(__int64 *, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  LPVOID v13; // rcx
  LPVOID v14; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-79h] BYREF
  __int128 v17; // [rsp+50h] [rbp-59h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-49h]
  VARIANTARG v19; // [rsp+70h] [rbp-39h] BYREF
  VARIANTARG v20; // [rsp+90h] [rbp-19h] BYREF
  VARIANTARG v21; // [rsp+B0h] [rbp+7h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v2 = SysAllocString(L"\\Microsoft\\Windows");
  v3 = SysAllocString(L"DiskDiagnostic");
  v4 = v3;
  if ( v2 && v3 )
  {
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, ppv);
    v6 = Instance;
    if ( Instance >= 0 )
    {
      v10 = (__int64 *)*ppv;
      v17 = *(_OWORD *)&pvarg.vt;
      v11 = *v10;
      pRecInfo = pvarg.pRecInfo;
      v19 = pvarg;
      v12 = *(__int64 (__fastcall **)(__int64 *, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v11 + 80);
      v20 = pvarg;
      v21 = pvarg;
      Instance = v12(v10, &v21, &v20, &v19, &v17);
      v6 = Instance;
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, LPVOID *))(*(_QWORD *)*ppv + 56LL))(*ppv, v2, ppv + 1);
        v6 = Instance;
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, LPVOID *))(*(_QWORD *)ppv[1] + 72LL))(
                       ppv[1],
                       v4,
                       ppv + 2);
          v6 = Instance;
          if ( Instance >= 0 )
          {
LABEL_31:
            SysFreeString(v2);
            goto LABEL_32;
          }
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 14;
            goto LABEL_7;
          }
        }
        else
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 13;
            goto LABEL_7;
          }
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 12;
          goto LABEL_7;
        }
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 11;
LABEL_7:
        v9 = (unsigned int)Instance;
LABEL_23:
        WPP_SF_d(v7[2], v8, WPP_4f3495666d7e372198f3636e22490d50_Traceguids, v9);
      }
    }
  }
  else
  {
    v6 = -2147024882;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 10;
      v9 = 2147942414LL;
      goto LABEL_23;
    }
  }
  v13 = ppv[2];
  if ( v13 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
    ppv[2] = 0;
  }
  v14 = ppv[1];
  if ( v14 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
    ppv[1] = 0;
  }
  if ( *ppv )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*ppv + 16LL))(*ppv);
    *ppv = 0;
  }
  if ( v2 )
    goto LABEL_31;
LABEL_32:
  if ( v4 )
    SysFreeString(v4);
  VariantClear(&pvarg);
  return v6;
}

```

## disassembly

```asm
0x180007340  push    rbp
0x180007342  push    rbx
0x180007343  push    rsi
0x180007344  push    rdi
0x180007345  push    r14
0x180007347  push    r15
0x180007349  lea     rbp, [rsp-2Fh]
0x18000734e  sub     rsp, 0D8h
0x180007355  mov     rdi, rcx
0x180007358  xorps   xmm0, xmm0
0x18000735b  xor     eax, eax
0x18000735d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180007361  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180007365  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180007369  call    cs:__imp_VariantInit
0x18000736f  lea     rcx, psz; "\\Microsoft\\Windows"
0x180007376  call    cs:__imp_SysAllocString
0x18000737c  lea     rcx, aDiskdiagnostic; "DiskDiagnostic"
0x180007383  mov     r14, rax
0x180007386  call    cs:__imp_SysAllocString
0x18000738c  mov     rsi, rax
0x18000738f  test    r14, r14
0x180007392  jz      loc_180007501
0x180007398  test    rax, rax
0x18000739b  jz      loc_180007501
0x1800073a1  xor     edx, edx; pUnkOuter
0x1800073a3  mov     [rsp+100h+ppv], rdi; ppv
0x1800073a8  lea     r9, IID_ITaskService; riid
0x1800073af  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800073b6  lea     r8d, [rdx+1]; dwClsContext
0x1800073ba  call    cs:__imp_CoCreateInstance
0x1800073c0  mov     ebx, eax
0x1800073c2  test    eax, eax
0x1800073c4  jns     short loc_1800073F4
0x1800073c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073cd  lea     rdx, WPP_GLOBAL_Control
0x1800073d4  cmp     rcx, rdx
0x1800073d7  jz      loc_18000753A
0x1800073dd  test    byte ptr [rcx+1Ch], 1
0x1800073e1  jz      loc_18000753A
0x1800073e7  mov     edx, 0Bh
0x1800073ec  mov     r9d, eax
0x1800073ef  jmp     loc_18000752A
0x1800073f4  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x1800073f8  lea     rdx, [rbp+57h+var_B0]
0x1800073fc  mov     rcx, [rdi]
0x1800073ff  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x180007404  lea     r9, [rbp+57h+var_90]
0x180007408  mov     [rsp+100h+ppv], rdx
0x18000740d  lea     r8, [rbp+57h+var_70]
0x180007411  lea     rdx, [rbp+57h+var_50]
0x180007415  movaps  [rbp+57h+var_B0], xmm1
0x180007419  mov     rax, [rcx]
0x18000741c  movsd   [rbp+57h+var_A0], xmm0
0x180007421  movaps  [rbp+57h+var_90], xmm1
0x180007425  movsd   [rbp+57h+var_80], xmm0
0x18000742a  mov     rax, [rax+50h]
0x18000742e  movaps  [rbp+57h+var_70], xmm1
0x180007432  movsd   [rbp+57h+var_60], xmm0
0x180007437  movaps  [rbp+57h+var_50], xmm1
0x18000743b  movsd   [rbp+57h+var_40], xmm0
0x180007440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007445  mov     ebx, eax
0x180007447  test    eax, eax
0x180007449  jns     short loc_180007476
0x18000744b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007452  lea     rdx, WPP_GLOBAL_Control
0x180007459  cmp     rcx, rdx
0x18000745c  jz      loc_18000753A
0x180007462  test    byte ptr [rcx+1Ch], 1
0x180007466  jz      loc_18000753A
0x18000746c  mov     edx, 0Ch
0x180007471  jmp     loc_1800073EC
0x180007476  mov     rcx, [rdi]
0x180007479  lea     r8, [rdi+8]
0x18000747d  mov     rdx, r14
0x180007480  mov     rax, [rcx]
0x180007483  mov     rax, [rax+38h]
0x180007487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000748c  mov     ebx, eax
0x18000748e  test    eax, eax
0x180007490  jns     short loc_1800074BD
0x180007492  mov     rcx, cs:WPP_GLOBAL_Control
0x180007499  lea     rdx, WPP_GLOBAL_Control
0x1800074a0  cmp     rcx, rdx
0x1800074a3  jz      loc_18000753A
0x1800074a9  test    byte ptr [rcx+1Ch], 1
0x1800074ad  jz      loc_18000753A
0x1800074b3  mov     edx, 0Dh
0x1800074b8  jmp     loc_1800073EC
0x1800074bd  mov     rcx, [rdi+8]
0x1800074c1  lea     r8, [rdi+10h]
0x1800074c5  mov     rdx, rsi
0x1800074c8  mov     rax, [rcx]
0x1800074cb  mov     rax, [rax+48h]
0x1800074cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074d4  mov     ebx, eax
0x1800074d6  test    eax, eax
0x1800074d8  jns     loc_180007594
0x1800074de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074e5  lea     rdx, WPP_GLOBAL_Control
0x1800074ec  cmp     rcx, rdx
0x1800074ef  jz      short loc_18000753A
0x1800074f1  test    byte ptr [rcx+1Ch], 1
0x1800074f5  jz      short loc_18000753A
0x1800074f7  mov     edx, 0Eh
0x1800074fc  jmp     loc_1800073EC
0x180007501  mov     ebx, 8007000Eh
0x180007506  mov     rcx, cs:WPP_GLOBAL_Control
0x18000750d  lea     rdx, WPP_GLOBAL_Control
0x180007514  cmp     rcx, rdx
0x180007517  jz      short loc_18000753A
0x180007519  test    byte ptr [rcx+1Ch], 1
0x18000751d  jz      short loc_18000753A
0x18000751f  mov     edx, 0Ah
0x180007524  mov     r9d, 8007000Eh
0x18000752a  mov     rcx, [rcx+10h]
0x18000752e  lea     r8, WPP_4f3495666d7e372198f3636e22490d50_Traceguids
0x180007535  call    WPP_SF_d
0x18000753a  mov     rcx, [rdi+10h]
0x18000753e  test    rcx, rcx
0x180007541  jz      short loc_180007557
0x180007543  mov     rax, [rcx]
0x180007546  mov     rax, [rax+10h]
0x18000754a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000754f  mov     qword ptr [rdi+10h], 0
0x180007557  mov     rcx, [rdi+8]
0x18000755b  test    rcx, rcx
0x18000755e  jz      short loc_180007574
0x180007560  mov     rax, [rcx]
0x180007563  mov     rax, [rax+10h]
0x180007567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000756c  mov     qword ptr [rdi+8], 0
0x180007574  mov     rcx, [rdi]
0x180007577  test    rcx, rcx
0x18000757a  jz      short loc_18000758F
0x18000757c  mov     rax, [rcx]
0x18000757f  mov     rax, [rax+10h]
0x180007583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007588  mov     qword ptr [rdi], 0
0x18000758f  test    r14, r14
0x180007592  jz      short loc_18000759D
0x180007594  mov     rcx, r14; bstrString
0x180007597  call    cs:__imp_SysFreeString
0x18000759d  test    rsi, rsi
0x1800075a0  jz      short loc_1800075AB
0x1800075a2  mov     rcx, rsi; bstrString
0x1800075a5  call    cs:__imp_SysFreeString
0x1800075ab  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800075af  call    cs:__imp_VariantClear
0x1800075b5  mov     eax, ebx
0x1800075b7  add     rsp, 0D8h
0x1800075be  pop     r15
0x1800075c0  pop     r14
0x1800075c2  pop     rdi
0x1800075c3  pop     rsi
0x1800075c4  pop     rbx
0x1800075c5  pop     rbp
0x1800075c6  retn
```
