# PlaTaskService::VerifyService(void)

- ea: `0x18001b050`
- end: `0x18001b2c3`
- name: `?VerifyService@PlaTaskService@@AEAAJXZ`
- size: `627`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019620`
- `0x1800e9cf0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18001b050`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b0b9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b0b9`
- `OLEAUT32!__imp_VariantInit` at `0x18001b08d`
- `OLEAUT32!__imp_VariantInit` at `0x18001b08d`
- `OLEAUT32!__imp_VariantClear` at `0x18001b128`
- `OLEAUT32!__imp_VariantClear` at `0x18001b128`

## string_xrefs

- `0x18001b1a7`: `PlaTaskService::VerifyService`

## pseudocode

```c
__int64 __fastcall PlaTaskService::VerifyService(LPVOID *ppv)
{
  int v2; // ebx
  HRESULT Instance; // eax
  __int64 *v4; // rcx
  __int64 v5; // rax
  __int64 (__fastcall *v6)(__int64 *, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  __int64 v8; // rax
  HRESULT *v9; // r9
  int *v10; // rcx
  __int64 v11; // rax
  int v12; // [rsp+70h] [rbp-90h] BYREF
  HRESULT v13; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  __int128 v15; // [rsp+A0h] [rbp-60h] BYREF
  IRecordInfo *pRecInfo; // [rsp+B0h] [rbp-50h]
  VARIANTARG v17; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v18; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG v19; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v20[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v21[64]; // [rsp+1A0h] [rbp+A0h] BYREF

  v2 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  if ( !*ppv )
  {
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, ppv);
    v2 = Instance;
    if ( Instance < 0 )
    {
      v12 = 0;
      v13 = Instance;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v20, 0x4000000000000800uLL);
        v8 = -1;
        do
          ++v8;
        while ( v20[v8] );
        v9 = &v13;
        v10 = &v12;
        goto LABEL_9;
      }
    }
    else
    {
      v4 = (__int64 *)*ppv;
      v15 = *(_OWORD *)&pvarg.vt;
      v5 = *v4;
      pRecInfo = pvarg.pRecInfo;
      v17 = pvarg;
      v6 = *(__int64 (__fastcall **)(__int64 *, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v5 + 80);
      v18 = pvarg;
      v19 = pvarg;
      v2 = v6(v4, &v19, &v18, &v17, &v15);
      if ( v2 < 0 )
      {
        if ( *ppv )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*ppv + 16LL))(*ppv);
          *ppv = 0;
        }
        v13 = 0;
        v12 = v2;
        if ( (_DWORD)xmmword_180169738 )
        {
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v21, 0x4000000000000800uLL);
            v11 = -1;
            do
              ++v11;
            while ( v21[v11] );
            v9 = &v12;
            v10 = &v13;
LABEL_9:
            EventingWriteEvent(
              &g_Eventing,
              PLA_EVENT_ERROR,
              5,
              v9,
              4,
              qword_180147320,
              1,
              v10,
              4,
              "PlaTaskService::VerifyService",
              30);
          }
        }
      }
    }
  }
  VariantClear(&pvarg);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001b050  push    rbp
0x18001b052  push    rbx
0x18001b053  push    rsi
0x18001b054  push    rdi
0x18001b055  lea     rbp, [rsp-138h]
0x18001b05d  sub     rsp, 238h
0x18001b064  mov     rax, cs:__security_cookie
0x18001b06b  xor     rax, rsp
0x18001b06e  mov     [rbp+150h+var_30], rax
0x18001b075  mov     rdi, rcx
0x18001b078  xorps   xmm0, xmm0
0x18001b07b  xor     eax, eax
0x18001b07d  lea     rcx, [rbp+150h+pvarg]; pvarg
0x18001b081  xor     esi, esi
0x18001b083  mov     qword ptr [rbp+150h+pvarg+10h], rax
0x18001b087  mov     ebx, esi
0x18001b089  movups  xmmword ptr [rbp+150h+pvarg], xmm0
0x18001b08d  call    cs:__imp_VariantInit
0x18001b093  mov     qword ptr [rbp+150h+pvarg+8], rsi
0x18001b097  cmp     [rdi], rsi
0x18001b09a  jnz     loc_18001B124
0x18001b0a0  lea     r9, IID_ITaskService; riid
0x18001b0a7  mov     [rsp+250h+ppv], rdi; ppv
0x18001b0ac  xor     edx, edx; pUnkOuter
0x18001b0ae  lea     r8d, [rsi+1]; dwClsContext
0x18001b0b2  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001b0b9  call    cs:__imp_CoCreateInstance
0x18001b0bf  mov     ebx, eax
0x18001b0c1  test    eax, eax
0x18001b0c3  js      loc_18001B24A
0x18001b0c9  movups  xmm1, xmmword ptr [rbp+150h+pvarg]
0x18001b0cd  lea     rdx, [rbp+150h+var_1B0]
0x18001b0d1  mov     rcx, [rdi]
0x18001b0d4  movsd   xmm0, qword ptr [rbp+150h+pvarg+10h]
0x18001b0d9  lea     r9, [rbp+150h+var_190]
0x18001b0dd  mov     [rsp+250h+ppv], rdx
0x18001b0e2  lea     r8, [rbp+150h+var_170]
0x18001b0e6  lea     rdx, [rbp+150h+var_150]
0x18001b0ea  movaps  [rbp+150h+var_1B0], xmm1
0x18001b0ee  mov     rax, [rcx]
0x18001b0f1  movsd   [rbp+150h+var_1A0], xmm0
0x18001b0f6  movaps  [rbp+150h+var_190], xmm1
0x18001b0fa  movsd   [rbp+150h+var_180], xmm0
0x18001b0ff  mov     rax, [rax+50h]
0x18001b103  movaps  [rbp+150h+var_170], xmm1
0x18001b107  movsd   [rbp+150h+var_160], xmm0
0x18001b10c  movaps  [rbp+150h+var_150], xmm1
0x18001b110  movsd   [rbp+150h+var_140], xmm0
0x18001b115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b11a  mov     ebx, eax
0x18001b11c  test    eax, eax
0x18001b11e  js      loc_18001B2AA
0x18001b124  lea     rcx, [rbp+150h+pvarg]; pvarg
0x18001b128  call    cs:__imp_VariantClear
0x18001b12e  mov     eax, ebx
0x18001b130  mov     rcx, [rbp+150h+var_30]
0x18001b137  xor     rcx, rsp; StackCookie
0x18001b13a  call    __security_check_cookie
0x18001b13f  add     rsp, 238h
0x18001b146  pop     rdi
0x18001b147  pop     rsi
0x18001b148  pop     rbx
0x18001b149  pop     rbp
0x18001b14a  retn
0x18001b14b  mov     rax, cs:qword_180169748
0x18001b152  and     rax, rdx
0x18001b155  cmp     cs:qword_180169748, rax
0x18001b15c  jnz     short loc_18001B124
0x18001b15e  lea     rcx, [rbp+150h+var_130]; unsigned __int16 *
0x18001b162  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001b167  lea     rcx, [rbp+150h+var_130]
0x18001b16b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b16f  inc     rax
0x18001b172  cmp     [rcx+rax*2], si
0x18001b176  jnz     short loc_18001B16F
0x18001b178  lea     ecx, [rax+rax]
0x18001b17b  add     rcx, 2
0x18001b17f  lea     rax, [rbp+150h+var_130]
0x18001b183  mov     [rsp+250h+var_1F0], rcx
0x18001b188  lea     r9, [rsp+250h+var_1D8]
0x18001b18d  lea     rcx, [rsp+250h+var_1E0]
0x18001b192  mov     [rsp+250h+var_1F8], rax
0x18001b197  lea     rdx, PLA_EVENT_ERROR
0x18001b19e  mov     [rsp+250h+var_200], 1Eh
0x18001b1a7  lea     rax, aPlataskservice_1; "PlaTaskService::VerifyService"
0x18001b1ae  mov     [rsp+250h+var_208], rax
0x18001b1b3  mov     eax, 4
0x18001b1b8  mov     [rsp+250h+var_210], rax
0x18001b1bd  mov     [rsp+250h+var_218], rcx
0x18001b1c2  lea     rcx, qword_180147320
0x18001b1c9  mov     [rsp+250h+var_220], 1
0x18001b1d2  mov     [rsp+250h+var_228], rcx
0x18001b1d7  lea     r8d, [rax+1]
0x18001b1db  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18001b1e2  mov     [rsp+250h+ppv], rax
0x18001b1e7  call    EventingWriteEvent
0x18001b1ec  jmp     loc_18001B124
0x18001b1f1  mov     rax, cs:qword_180169748
0x18001b1f8  and     rax, rdx
0x18001b1fb  cmp     cs:qword_180169748, rax
0x18001b202  jnz     loc_18001B124
0x18001b208  lea     rcx, [rbp+150h+var_B0]; unsigned __int16 *
0x18001b20f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001b214  lea     rcx, [rbp+150h+var_B0]
0x18001b21b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b21f  inc     rax
0x18001b222  cmp     [rcx+rax*2], si
0x18001b226  jnz     short loc_18001B21F
0x18001b228  lea     ecx, [rax+rax]
0x18001b22b  add     rcx, 2
0x18001b22f  lea     rax, [rbp+150h+var_B0]
0x18001b236  mov     [rsp+250h+var_1F0], rcx
0x18001b23b  lea     r9, [rsp+250h+var_1E0]
0x18001b240  lea     rcx, [rsp+250h+var_1D8]
0x18001b245  jmp     loc_18001B192
0x18001b24a  cmp     dword ptr cs:xmmword_180169738, esi
0x18001b250  mov     [rsp+250h+var_1E0], esi
0x18001b254  mov     [rsp+250h+var_1D8], eax
0x18001b258  jz      loc_18001B124
0x18001b25e  mov     rdx, 4000000000000800h; unsigned __int64
0x18001b268  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001b26f  jz      loc_18001B124
0x18001b275  jmp     loc_18001B14B
0x18001b27a  cmp     dword ptr cs:xmmword_180169738, esi
0x18001b280  mov     [rsp+250h+var_1D8], esi
0x18001b284  mov     [rsp+250h+var_1E0], ebx
0x18001b288  jz      loc_18001B124
0x18001b28e  mov     rdx, 4000000000000800h; unsigned __int64
0x18001b298  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001b29f  jz      loc_18001B124
0x18001b2a5  jmp     loc_18001B1F1
0x18001b2aa  mov     rcx, [rdi]
0x18001b2ad  test    rcx, rcx
0x18001b2b0  jz      short loc_18001B27A
0x18001b2b2  mov     rax, [rcx]
0x18001b2b5  mov     rax, [rax+10h]
0x18001b2b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2be  mov     [rdi], rsi
0x18001b2c1  jmp     short loc_18001B27A
```
