# CfgMgrHelper::QueryNodeValue(ushort const *,ushort * *,ulong *)

- ea: `0x180036414`
- end: `0x180036614`
- name: `?QueryNodeValue@CfgMgrHelper@@QEAAJPEBGPEAPEAGPEAK@Z`
- size: `512`
- prototype: `__int64 __fastcall(LPVOID *ppv, OLECHAR *psz, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014d68`

## callees

- `0x180007ed4`
- `0x180036414`
- `0x180037aa8`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036598`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036598`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036589`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036589`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036483`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036483`
- `OLEAUT32!__imp_SysAllocString` at `0x18003649a`
- `OLEAUT32!__imp_SysAllocString` at `0x18003649a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800365f3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800365f3`
- `OLEAUT32!__imp_VariantInit` at `0x18003645f`
- `OLEAUT32!__imp_VariantInit` at `0x18003645f`
- `OLEAUT32!__imp_VariantClear` at `0x1800365d0`
- `OLEAUT32!__imp_VariantClear` at `0x1800365d0`
- `OLEAUT32!__imp_VariantChangeType` at `0x180036532`
- `OLEAUT32!__imp_VariantChangeType` at `0x180036532`

## pseudocode

```c
__int64 __fastcall CfgMgrHelper::QueryNodeValue(LPVOID *ppv, OLECHAR *psz, unsigned __int16 **a3, unsigned int *a4)
{
  HRESULT Instance; // ebx
  OLECHAR *v9; // rdi
  BSTR v10; // rax
  BSTR bstrVal; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v15; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  int v18; // [rsp+80h] [rbp+30h] BYREF
  __int64 v19; // [rsp+90h] [rbp+40h] BYREF

  v19 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v18 = 0;
  if ( *a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(ppv, psz, a3, a4);
  VariantInit(&pvarg);
  if ( !*ppv )
  {
    Instance = CoCreateInstance(
                 &GUID_66d0db14_5638_475f_a386_629522d8c461,
                 0,
                 1u,
                 &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
                 ppv);
    if ( Instance < 0 )
    {
      v9 = 0;
      goto LABEL_23;
    }
  }
  v10 = SysAllocString(psz);
  v9 = v10;
  if ( !v10 )
    goto LABEL_7;
  Instance = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int64 *))(*(_QWORD *)*ppv + 80LL))(*ppv, v10, &v19);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 224LL))(v19, &v18);
    if ( Instance >= 0 )
    {
      if ( v18 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v19 + 104LL))(v19, &pvarg);
        if ( Instance >= 0 )
        {
          Instance = VariantChangeType(&pvarg, &pvarg, 0, 8u);
          if ( Instance >= 0 )
          {
            bstrVal = pvarg.bstrVal;
            if ( pvarg.llVal )
            {
              v12 = 0x7FFFFFFF;
              do
              {
                if ( !*bstrVal )
                  break;
                ++bstrVal;
                --v12;
              }
              while ( v12 );
              Instance = v12 == 0 ? 0x80070057 : 0;
              if ( v12 )
              {
                v13 = ((0x7FFFFFFF - v12) & -(__int64)(v12 != 0)) + 1;
                ProcessHeap = GetProcessHeap();
                v15 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2 * v13);
                *a3 = v15;
                if ( !v15 )
                {
LABEL_7:
                  Instance = -2147024882;
                  goto LABEL_23;
                }
                Instance = StringCchCopyW(v15, v13, pvarg.bstrVal);
                if ( Instance >= 0 )
                {
                  *a4 = v13;
                  Instance = 0;
                }
              }
            }
            else
            {
              Instance = -2147024809;
            }
          }
        }
      }
      else
      {
        Instance = -2147418113;
      }
    }
  }
LABEL_23:
  VariantClear(&pvarg);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v9 )
    SysFreeString(v9);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180036414  mov     [rsp-28h+arg_8], rbx
0x180036419  mov     [rsp-28h+arg_18], rsi
0x18003641e  push    rbp
0x18003641f  push    rdi
0x180036420  push    r12
0x180036422  push    r14
0x180036424  push    r15
0x180036426  mov     rbp, rsp
0x180036429  sub     rsp, 50h
0x18003642d  mov     r15, r9
0x180036430  mov     r14, r8
0x180036433  mov     rdi, rdx
0x180036436  mov     rsi, rcx
0x180036439  xor     r12d, r12d
0x18003643c  mov     [rbp+arg_10], r12
0x180036440  xorps   xmm0, xmm0
0x180036443  xor     eax, eax
0x180036445  movups  xmmword ptr [rbp+pvarg], xmm0
0x180036449  mov     qword ptr [rbp+pvarg+10h], rax
0x18003644d  mov     [rbp+arg_0], r12d
0x180036451  cmp     [r8], r12
0x180036454  jz      short loc_18003645B
0x180036456  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003645b  lea     rcx, [rbp+pvarg]; pvarg
0x18003645f  call    cs:__imp_VariantInit
0x180036465  cmp     [rsi], r12
0x180036468  jnz     short loc_180036497
0x18003646a  mov     [rsp+50h+ppv], rsi; ppv
0x18003646f  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180036476  xor     edx, edx; pUnkOuter
0x180036478  lea     r8d, [rdx+1]; dwClsContext
0x18003647c  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180036483  call    cs:__imp_CoCreateInstance
0x180036489  mov     ebx, eax
0x18003648b  test    eax, eax
0x18003648d  jns     short loc_180036497
0x18003648f  mov     rdi, r12
0x180036492  jmp     loc_1800365CC
0x180036497  mov     rcx, rdi; psz
0x18003649a  call    cs:__imp_SysAllocString
0x1800364a0  mov     rdi, rax
0x1800364a3  test    rax, rax
0x1800364a6  jnz     short loc_1800364B2
0x1800364a8  mov     ebx, 8007000Eh
0x1800364ad  jmp     loc_1800365CC
0x1800364b2  mov     rcx, [rsi]
0x1800364b5  mov     rax, [rcx]
0x1800364b8  lea     r8, [rbp+arg_10]
0x1800364bc  mov     rdx, rdi
0x1800364bf  mov     rax, [rax+50h]
0x1800364c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364c8  mov     ebx, eax
0x1800364ca  test    eax, eax
0x1800364cc  js      loc_1800365CC
0x1800364d2  mov     rcx, [rbp+arg_10]
0x1800364d6  mov     rax, [rcx]
0x1800364d9  lea     rdx, [rbp+arg_0]
0x1800364dd  mov     rax, [rax+0E0h]
0x1800364e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364e9  mov     ebx, eax
0x1800364eb  test    eax, eax
0x1800364ed  js      loc_1800365CC
0x1800364f3  cmp     [rbp+arg_0], r12d
0x1800364f7  jnz     short loc_180036503
0x1800364f9  mov     ebx, 8000FFFFh
0x1800364fe  jmp     loc_1800365CC
0x180036503  mov     rcx, [rbp+arg_10]
0x180036507  mov     rax, [rcx]
0x18003650a  lea     rdx, [rbp+pvarg]
0x18003650e  mov     rax, [rax+68h]
0x180036512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036517  mov     ebx, eax
0x180036519  test    eax, eax
0x18003651b  js      loc_1800365CC
0x180036521  mov     r9d, 8; vt
0x180036527  xor     r8d, r8d; wFlags
0x18003652a  lea     rdx, [rbp+pvarg]; pvarSrc
0x18003652e  lea     rcx, [rbp+pvarg]; pvargDest
0x180036532  call    cs:__imp_VariantChangeType
0x180036538  mov     ebx, eax
0x18003653a  test    eax, eax
0x18003653c  js      loc_1800365CC
0x180036542  mov     rax, qword ptr [rbp+pvarg+8]
0x180036546  test    rax, rax
0x180036549  jz      short loc_1800365C7
0x18003654b  mov     edx, 7FFFFFFFh
0x180036550  mov     ecx, edx
0x180036552  cmp     [rax], r12w
0x180036556  jz      short loc_180036562
0x180036558  add     rax, 2
0x18003655c  sub     rcx, 1
0x180036560  jnz     short loc_180036552
0x180036562  mov     rax, rcx
0x180036565  neg     rax
0x180036568  sbb     ebx, ebx
0x18003656a  not     ebx
0x18003656c  and     ebx, 80070057h
0x180036572  mov     rax, rcx
0x180036575  sub     rdx, rcx
0x180036578  neg     rax
0x18003657b  sbb     rsi, rsi
0x18003657e  and     rsi, rdx
0x180036581  test    rcx, rcx
0x180036584  jz      short loc_1800365CC
0x180036586  inc     rsi
0x180036589  call    cs:__imp_GetProcessHeap
0x18003658f  lea     r8, [rsi+rsi]; dwBytes
0x180036593  xor     edx, edx; dwFlags
0x180036595  mov     rcx, rax; hHeap
0x180036598  call    cs:__imp_HeapAlloc
0x18003659e  mov     [r14], rax
0x1800365a1  test    rax, rax
0x1800365a4  jz      loc_1800364A8
0x1800365aa  mov     r8, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x1800365ae  mov     rdx, rsi; unsigned __int64
0x1800365b1  mov     rcx, rax; unsigned __int16 *
0x1800365b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800365b9  mov     ebx, eax
0x1800365bb  test    eax, eax
0x1800365bd  js      short loc_1800365CC
0x1800365bf  mov     [r15], esi
0x1800365c2  mov     ebx, r12d
0x1800365c5  jmp     short loc_1800365CC
0x1800365c7  mov     ebx, 80070057h
0x1800365cc  lea     rcx, [rbp+pvarg]; pvarg
0x1800365d0  call    cs:__imp_VariantClear
0x1800365d6  mov     rcx, [rbp+arg_10]
0x1800365da  test    rcx, rcx
0x1800365dd  jz      short loc_1800365EB
0x1800365df  mov     rax, [rcx]
0x1800365e2  mov     rax, [rax+10h]
0x1800365e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365eb  test    rdi, rdi
0x1800365ee  jz      short loc_1800365F9
0x1800365f0  mov     rcx, rdi; bstrString
0x1800365f3  call    cs:__imp_SysFreeString
0x1800365f9  mov     eax, ebx
0x1800365fb  lea     r11, [rsp+50h+var_s0]
0x180036600  mov     rbx, [r11+38h]
0x180036604  mov     rsi, [r11+48h]
0x180036608  mov     rsp, r11
0x18003660b  pop     r15
0x18003660d  pop     r14
0x18003660f  pop     r12
0x180036611  pop     rdi
0x180036612  pop     rbp
0x180036613  retn
```
