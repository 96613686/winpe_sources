# GetCalibrationTask(IRegisteredTask * *)

- ea: `0x180049040`
- end: `0x180049219`
- name: `?GetCalibrationTask@@YAJPEAPEAUIRegisteredTask@@@Z`
- size: `473`
- prototype: `__int64 __fastcall(struct IRegisteredTask **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004ba30`

## callees

- `0x180049040`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004908c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800490ad`
- `OLEAUT32!__imp_SysAllocString` at `0x18004908c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800490ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800491fa`
- `OLEAUT32!__imp_SysFreeString` at `0x180049203`
- `OLEAUT32!__imp_SysFreeString` at `0x1800491fa`
- `OLEAUT32!__imp_SysFreeString` at `0x180049203`
- `OLEAUT32!__imp_VariantInit` at `0x18004907f`
- `OLEAUT32!__imp_VariantInit` at `0x18004907f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800490d8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800490d8`

## pseudocode

```c
__int64 __fastcall GetCalibrationTask(struct IRegisteredTask **a1)
{
  OLECHAR *v2; // rsi
  OLECHAR *v3; // rdi
  HRESULT v4; // ebx
  __int64 v5; // rax
  __int64 (__fastcall *v6)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  struct IRegisteredTask *v7; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-69h] BYREF
  __int128 v10; // [rsp+50h] [rbp-49h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-39h]
  VARIANTARG v12; // [rsp+70h] [rbp-29h] BYREF
  VARIANTARG v13; // [rsp+90h] [rbp-9h] BYREF
  VARIANTARG v14; // [rsp+B0h] [rbp+17h] BYREF
  struct IRegisteredTask *v15; // [rsp+108h] [rbp+6Fh] BYREF
  LPVOID ppv; // [rsp+110h] [rbp+77h] BYREF
  __int64 v17; // [rsp+118h] [rbp+7Fh] BYREF

  ppv = 0;
  v17 = 0;
  v15 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v2 = SysAllocString(L"Microsoft\\Windows\\WindowsColorSystem");
  if ( !v2 )
  {
    v3 = 0;
LABEL_3:
    v4 = -2147024882;
    goto LABEL_11;
  }
  v3 = SysAllocString(L"Calibration Loader");
  if ( !v3 )
    goto LABEL_3;
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v4 >= 0 )
  {
    v10 = *(_OWORD *)&pvarg.vt;
    v5 = *(_QWORD *)ppv;
    pRecInfo = pvarg.pRecInfo;
    v12 = pvarg;
    v6 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v5 + 80);
    v13 = pvarg;
    v14 = pvarg;
    v4 = v6(ppv, &v14, &v13, &v12, &v10);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v2, &v17);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, struct IRegisteredTask **))(*(_QWORD *)v17 + 104LL))(
               v17,
               v3,
               &v15);
        if ( v4 >= 0 )
        {
          v7 = v15;
          *a1 = v15;
          if ( !v7 )
            goto LABEL_12;
          ((void (__fastcall *)(struct IRegisteredTask *))v7->lpVtbl->AddRef)(v7);
        }
      }
    }
  }
LABEL_11:
  v7 = v15;
LABEL_12:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v7 = v15;
    ppv = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v7 = v15;
    v17 = 0;
  }
  if ( v7 )
  {
    ((void (__fastcall *)(struct IRegisteredTask *))v7->lpVtbl->Release)(v7);
    v15 = 0;
  }
  SysFreeString(v2);
  SysFreeString(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180049040  push    rbp
0x180049042  push    rbx
0x180049043  push    rsi
0x180049044  push    rdi
0x180049045  push    r14
0x180049047  lea     rbp, [rsp-37h]
0x18004904c  sub     rsp, 0D0h
0x180049053  mov     r14, rcx
0x180049056  mov     [rbp+57h+arg_10], 0
0x18004905e  xorps   xmm0, xmm0
0x180049061  mov     [rbp+57h+arg_18], 0
0x180049069  xor     eax, eax
0x18004906b  mov     [rbp+57h+arg_8], 0
0x180049073  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180049077  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18004907b  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18004907f  call    cs:__imp_VariantInit
0x180049085  lea     rcx, aMicrosoftWindo; "Microsoft\\Windows\\WindowsColorSystem"
0x18004908c  call    cs:__imp_SysAllocString
0x180049092  mov     rsi, rax
0x180049095  test    rax, rax
0x180049098  jnz     short loc_1800490A6
0x18004909a  xor     edi, edi
0x18004909c  mov     ebx, 8007000Eh
0x1800490a1  jmp     loc_180049192
0x1800490a6  lea     rcx, aCalibrationLoa; "Calibration Loader"
0x1800490ad  call    cs:__imp_SysAllocString
0x1800490b3  mov     rdi, rax
0x1800490b6  test    rax, rax
0x1800490b9  jz      short loc_18004909C
0x1800490bb  xor     edx, edx; pUnkOuter
0x1800490bd  lea     rax, [rbp+57h+arg_10]
0x1800490c1  lea     r9, IID_ITaskService; riid
0x1800490c8  mov     [rsp+0F0h+ppv], rax; ppv
0x1800490cd  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800490d4  lea     r8d, [rdx+1]; dwClsContext
0x1800490d8  call    cs:__imp_CoCreateInstance
0x1800490de  mov     ebx, eax
0x1800490e0  test    eax, eax
0x1800490e2  js      loc_180049192
0x1800490e8  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x1800490ec  lea     rdx, [rbp+57h+var_A0]
0x1800490f0  mov     rcx, [rbp+57h+arg_10]
0x1800490f4  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x1800490f9  lea     r9, [rbp+57h+var_80]
0x1800490fd  mov     [rsp+0F0h+ppv], rdx
0x180049102  lea     r8, [rbp+57h+var_60]
0x180049106  lea     rdx, [rbp+57h+var_40]
0x18004910a  movaps  [rbp+57h+var_A0], xmm1
0x18004910e  mov     rax, [rcx]
0x180049111  movsd   [rbp+57h+var_90], xmm0
0x180049116  movaps  [rbp+57h+var_80], xmm1
0x18004911a  movsd   [rbp+57h+var_70], xmm0
0x18004911f  mov     rax, [rax+50h]
0x180049123  movaps  [rbp+57h+var_60], xmm1
0x180049127  movsd   [rbp+57h+var_50], xmm0
0x18004912c  movaps  [rbp+57h+var_40], xmm1
0x180049130  movsd   [rbp+57h+var_30], xmm0
0x180049135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004913a  mov     ebx, eax
0x18004913c  test    eax, eax
0x18004913e  js      short loc_180049192
0x180049140  mov     rcx, [rbp+57h+arg_10]
0x180049144  lea     r8, [rbp+57h+arg_18]
0x180049148  mov     rdx, rsi
0x18004914b  mov     rax, [rcx]
0x18004914e  mov     rax, [rax+38h]
0x180049152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049157  mov     ebx, eax
0x180049159  test    eax, eax
0x18004915b  js      short loc_180049192
0x18004915d  mov     rcx, [rbp+57h+arg_18]
0x180049161  lea     r8, [rbp+57h+arg_8]
0x180049165  mov     rdx, rdi
0x180049168  mov     rax, [rcx]
0x18004916b  mov     rax, [rax+68h]
0x18004916f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049174  mov     ebx, eax
0x180049176  test    eax, eax
0x180049178  js      short loc_180049192
0x18004917a  mov     rcx, [rbp+57h+arg_8]
0x18004917e  mov     [r14], rcx
0x180049181  test    rcx, rcx
0x180049184  jz      short loc_180049196
0x180049186  mov     rax, [rcx]
0x180049189  mov     rax, [rax+8]
0x18004918d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049192  mov     rcx, [rbp+57h+arg_8]
0x180049196  mov     rdx, [rbp+57h+arg_10]
0x18004919a  test    rdx, rdx
0x18004919d  jz      short loc_1800491BA
0x18004919f  mov     rax, [rdx]
0x1800491a2  mov     rcx, rdx
0x1800491a5  mov     rax, [rax+10h]
0x1800491a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800491ae  mov     rcx, [rbp+57h+arg_8]
0x1800491b2  mov     [rbp+57h+arg_10], 0
0x1800491ba  mov     rdx, [rbp+57h+arg_18]
0x1800491be  test    rdx, rdx
0x1800491c1  jz      short loc_1800491DE
0x1800491c3  mov     rax, [rdx]
0x1800491c6  mov     rcx, rdx
0x1800491c9  mov     rax, [rax+10h]
0x1800491cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800491d2  mov     rcx, [rbp+57h+arg_8]
0x1800491d6  mov     [rbp+57h+arg_18], 0
0x1800491de  test    rcx, rcx
0x1800491e1  jz      short loc_1800491F7
0x1800491e3  mov     rax, [rcx]
0x1800491e6  mov     rax, [rax+10h]
0x1800491ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800491ef  mov     [rbp+57h+arg_8], 0
0x1800491f7  mov     rcx, rsi; bstrString
0x1800491fa  call    cs:__imp_SysFreeString
0x180049200  mov     rcx, rdi; bstrString
0x180049203  call    cs:__imp_SysFreeString
0x180049209  mov     eax, ebx
0x18004920b  add     rsp, 0D0h
0x180049212  pop     r14
0x180049214  pop     rdi
0x180049215  pop     rsi
0x180049216  pop     rbx
0x180049217  pop     rbp
0x180049218  retn
```
