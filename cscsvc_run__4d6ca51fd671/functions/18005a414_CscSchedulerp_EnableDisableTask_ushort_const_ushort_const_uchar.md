# CscSchedulerp_EnableDisableTask(ushort const *,ushort const *,uchar)

- ea: `0x18005a414`
- end: `0x18005a66e`
- name: `?CscSchedulerp_EnableDisableTask@@YAJPEBG0E@Z`
- size: `602`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005a240`

## callees

- `0x180036394`
- `0x18003c460`
- `0x180044554`
- `0x18005a414`
- `0x180089010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18005a486`
- `OLEAUT32!__imp_VariantInit` at `0x18005a486`
- `OLEAUT32!__imp_VariantClear` at `0x18005a4f5`
- `OLEAUT32!__imp_VariantClear` at `0x18005a4f5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a45e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a45e`

## pseudocode

```c
__int64 __fastcall CscSchedulerp_EnableDisableTask(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int8 a3)
{
  int v4; // edi
  HRESULT v5; // ebx
  __int64 v6; // rax
  __int64 (__fastcall *v7)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *); // rax
  LPVOID ppv; // [rsp+38h] [rbp-69h] BYREF
  __int64 v10; // [rsp+40h] [rbp-61h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-59h] BYREF
  __int128 v12; // [rsp+68h] [rbp-39h] BYREF
  IRecordInfo *pRecInfo; // [rsp+78h] [rbp-29h]
  __int128 v14; // [rsp+88h] [rbp-19h] BYREF
  IRecordInfo *v15; // [rsp+98h] [rbp-9h]
  __int128 v16; // [rsp+A8h] [rbp+7h] BYREF
  IRecordInfo *v17; // [rsp+B8h] [rbp+17h]
  __int128 v18; // [rsp+C8h] [rbp+27h] BYREF
  IRecordInfo *v19; // [rsp+D8h] [rbp+37h]
  const unsigned __int16 *v20; // [rsp+108h] [rbp+67h] BYREF
  __int64 v21; // [rsp+120h] [rbp+7Fh] BYREF

  v20 = a1;
  v4 = a3;
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v5 >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    pvarg.llVal = 0;
    pvarg.vt = 1;
    v6 = *(_QWORD *)ppv;
    pRecInfo = pvarg.pRecInfo;
    v12 = *(unsigned __int64 *)&pvarg.vt;
    v14 = *(unsigned __int64 *)&pvarg.vt;
    v7 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *))(v6 + 80);
    v15 = pvarg.pRecInfo;
    v16 = *(unsigned __int64 *)&pvarg.vt;
    v17 = pvarg.pRecInfo;
    v18 = *(unsigned __int64 *)&pvarg.vt;
    v19 = pvarg.pRecInfo;
    v5 = v7(ppv, &v18, &v16, &v14, &v12);
    VariantClear(&pvarg);
    if ( v5 >= 0 )
    {
      v10 = 0;
      v5 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 56LL))(
             ppv,
             L"\\Microsoft\\Windows\\Offline Files",
             &v10);
      if ( v5 >= 0 )
      {
        v21 = 0;
        v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v10 + 104LL))(
               v10,
               a2,
               &v21);
        if ( v5 >= 0 )
        {
          LOWORD(v20) = 0;
          v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v21 + 80LL))(v21, &v20);
          if ( v5 < 0 || (_WORD)v20 == -((_BYTE)v4 != 0) )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_86066e28a589341160dd1d02cee7a47b_Traceguids);
            }
          }
          else
          {
            v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 88LL))(v21);
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
            {
              WPP_SF_dS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                16,
                (unsigned int)WPP_86066e28a589341160dd1d02cee7a47b_Traceguids,
                v4,
                (__int64)a2);
            }
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_86066e28a589341160dd1d02cee7a47b_Traceguids, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005a414  mov     rax, rsp
0x18005a417  mov     [rax+10h], rbx
0x18005a41b  mov     [rax+18h], rsi
0x18005a41f  mov     [rax+8], rcx
0x18005a423  push    rbp
0x18005a424  push    rdi
0x18005a425  push    r13
0x18005a427  lea     rbp, [rax-5Fh]
0x18005a42b  sub     rsp, 0E0h
0x18005a432  mov     rsi, rdx
0x18005a435  movzx   edi, r8b
0x18005a439  xor     edx, edx; pUnkOuter
0x18005a43b  mov     [rbp+57h+var_C0], 0
0x18005a443  lea     rax, [rbp+57h+var_C0]
0x18005a447  lea     r9, IID_ITaskService; riid
0x18005a44e  mov     [rsp+0F0h+ppv], rax; ppv
0x18005a453  lea     rcx, CLSID_TaskScheduler; rclsid
0x18005a45a  lea     r8d, [rdx+1]; dwClsContext
0x18005a45e  call    cs:__imp_CoCreateInstance
0x18005a464  lea     r13, WPP_GLOBAL_Control
0x18005a46b  mov     ebx, eax
0x18005a46d  test    eax, eax
0x18005a46f  js      loc_18005A627
0x18005a475  xorps   xmm0, xmm0
0x18005a478  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005a47c  xor     eax, eax
0x18005a47e  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18005a482  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18005a486  call    cs:__imp_VariantInit
0x18005a48c  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18005a491  lea     rdx, [rbp+57h+var_90]
0x18005a495  mov     rcx, [rbp+57h+var_C0]
0x18005a499  lea     r9, [rbp+57h+var_70]
0x18005a49d  mov     qword ptr [rbp+57h+pvarg+8], 0
0x18005a4a5  lea     r8, [rbp+57h+var_50]
0x18005a4a9  mov     eax, 1
0x18005a4ae  mov     [rsp+0F0h+ppv], rdx
0x18005a4b3  mov     word ptr [rbp+57h+pvarg], ax
0x18005a4b7  lea     rdx, [rbp+57h+var_30]
0x18005a4bb  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18005a4bf  mov     rax, [rcx]
0x18005a4c2  movsd   [rbp+57h+var_80], xmm0
0x18005a4c7  movaps  [rbp+57h+var_90], xmm1
0x18005a4cb  movaps  [rbp+57h+var_70], xmm1
0x18005a4cf  mov     rax, [rax+50h]
0x18005a4d3  movsd   [rbp+57h+var_60], xmm0
0x18005a4d8  movaps  [rbp+57h+var_50], xmm1
0x18005a4dc  movsd   [rbp+57h+var_40], xmm0
0x18005a4e1  movaps  [rbp+57h+var_30], xmm1
0x18005a4e5  movsd   [rbp+57h+var_20], xmm0
0x18005a4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a4ef  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005a4f3  mov     ebx, eax
0x18005a4f5  call    cs:__imp_VariantClear
0x18005a4fb  test    ebx, ebx
0x18005a4fd  js      loc_18005A617
0x18005a503  mov     rcx, [rbp+57h+var_C0]
0x18005a507  lea     r8, [rbp+57h+var_B8]
0x18005a50b  mov     [rbp+57h+var_B8], 0
0x18005a513  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Offline Files"
0x18005a51a  mov     rax, [rcx]
0x18005a51d  mov     rax, [rax+38h]
0x18005a521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a526  mov     ebx, eax
0x18005a528  test    eax, eax
0x18005a52a  js      loc_18005A617
0x18005a530  mov     rcx, [rbp+57h+var_B8]
0x18005a534  lea     r8, [rbp+57h+arg_18]
0x18005a538  mov     [rbp+57h+arg_18], 0
0x18005a540  mov     rdx, rsi
0x18005a543  mov     rax, [rcx]
0x18005a546  mov     rax, [rax+68h]
0x18005a54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a54f  mov     ebx, eax
0x18005a551  test    eax, eax
0x18005a553  js      loc_18005A607
0x18005a559  mov     rcx, [rbp+57h+arg_18]
0x18005a55d  lea     rdx, [rbp+57h+arg_0]
0x18005a561  xor     eax, eax
0x18005a563  mov     word ptr [rbp+57h+arg_0], ax
0x18005a567  mov     rax, [rcx]
0x18005a56a  mov     rax, [rax+50h]
0x18005a56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a573  mov     ebx, eax
0x18005a575  test    eax, eax
0x18005a577  js      short loc_18005A5CD
0x18005a579  mov     al, dil
0x18005a57c  neg     al
0x18005a57e  sbb     dx, dx
0x18005a581  cmp     word ptr [rbp+57h+arg_0], dx
0x18005a585  jz      short loc_18005A5CD
0x18005a587  mov     rcx, [rbp+57h+arg_18]
0x18005a58b  mov     rax, [rcx]
0x18005a58e  mov     rax, [rax+58h]
0x18005a592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a597  mov     ebx, eax
0x18005a599  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a5a0  cmp     rcx, r13
0x18005a5a3  jz      short loc_18005A5F7
0x18005a5a5  test    dword ptr [rcx+1Ch], 8000000h
0x18005a5ac  jz      short loc_18005A5F7
0x18005a5ae  mov     rcx, [rcx+10h]
0x18005a5b2  lea     r8, WPP_86066e28a589341160dd1d02cee7a47b_Traceguids
0x18005a5b9  mov     r9d, edi
0x18005a5bc  mov     [rsp+0F0h+ppv], rsi
0x18005a5c1  mov     edx, 10h
0x18005a5c6  call    WPP_SF_dS
0x18005a5cb  jmp     short loc_18005A5F7
0x18005a5cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a5d4  cmp     rcx, r13
0x18005a5d7  jz      short loc_18005A5F7
0x18005a5d9  test    dword ptr [rcx+1Ch], 8000000h
0x18005a5e0  jz      short loc_18005A5F7
0x18005a5e2  mov     rcx, [rcx+10h]
0x18005a5e6  lea     r8, WPP_86066e28a589341160dd1d02cee7a47b_Traceguids
0x18005a5ed  mov     edx, 11h
0x18005a5f2  call    WPP_SF_
0x18005a5f7  mov     rcx, [rbp+57h+arg_18]
0x18005a5fb  mov     rax, [rcx]
0x18005a5fe  mov     rax, [rax+10h]
0x18005a602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a607  mov     rcx, [rbp+57h+var_B8]
0x18005a60b  mov     rax, [rcx]
0x18005a60e  mov     rax, [rax+10h]
0x18005a612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a617  mov     rcx, [rbp+57h+var_C0]
0x18005a61b  mov     rax, [rcx]
0x18005a61e  mov     rax, [rax+10h]
0x18005a622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a627  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a62e  cmp     rcx, r13
0x18005a631  jz      short loc_18005A654
0x18005a633  test    dword ptr [rcx+1Ch], 8000000h
0x18005a63a  jz      short loc_18005A654
0x18005a63c  mov     rcx, [rcx+10h]
0x18005a640  lea     r8, WPP_86066e28a589341160dd1d02cee7a47b_Traceguids
0x18005a647  mov     edx, 12h
0x18005a64c  mov     r9d, ebx
0x18005a64f  call    WPP_SF_d
0x18005a654  lea     r11, [rsp+0F0h+var_10]
0x18005a65c  mov     eax, ebx
0x18005a65e  mov     rbx, [r11+28h]
0x18005a662  mov     rsi, [r11+30h]
0x18005a666  mov     rsp, r11
0x18005a669  pop     r13
0x18005a66b  pop     rdi
0x18005a66c  pop     rbp
0x18005a66d  retn
```
