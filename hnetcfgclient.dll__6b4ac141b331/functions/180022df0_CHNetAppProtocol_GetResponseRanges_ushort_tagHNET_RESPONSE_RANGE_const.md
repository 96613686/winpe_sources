# CHNetAppProtocol::GetResponseRanges(ushort *,tagHNET_RESPONSE_RANGE * * const)

- ea: `0x180022df0`
- end: `0x180022fd8`
- name: `?GetResponseRanges@CHNetAppProtocol@@UEAAJPEAGQEAPEAUtagHNET_RESPONSE_RANGE@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(CHNetAppProtocol *this, unsigned __int16 *, LPVOID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180022df0`
- `0x180028674`
- `0x180029a3c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180022e2d`
- `OLEAUT32!__imp_VariantInit` at `0x180022e2d`
- `OLEAUT32!__imp_VariantClear` at `0x180022ea5`
- `OLEAUT32!__imp_VariantClear` at `0x180022f91`
- `OLEAUT32!__imp_VariantClear` at `0x180022ea5`
- `OLEAUT32!__imp_VariantClear` at `0x180022f91`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180022f19`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180022f19`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180022f87`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180022f87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022eb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022eb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022fae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022fae`

## pseudocode

```c
__int64 __fastcall CHNetAppProtocol::GetResponseRanges(CHNetAppProtocol *this, unsigned __int16 *a2, LPVOID *a3)
{
  HRESULT WmiObjectFromPath; // ebx
  __int64 uiVal; // rsi
  struct tagHNET_RESPONSE_RANGE *v8; // rax
  unsigned __int16 i; // r14
  void *ppvData; // [rsp+40h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-18h] BYREF
  struct IWbemClassObject *v13; // [rsp+A0h] [rbp+40h] BYREF
  struct IWbemClassObject *v14; // [rsp+A8h] [rbp+48h] BYREF

  v13 = 0;
  ppvData = 0;
  v14 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  if ( a2 )
  {
    *a2 = 0;
    WmiObjectFromPath = GetWmiObjectFromPath(
                          *((struct IWbemServices **)this + 8),
                          *((unsigned __int16 **)this + 9),
                          &v13);
    if ( !WmiObjectFromPath )
    {
      LOWORD(uiVal) = 0;
      WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v13->lpVtbl->Get)(
                            v13,
                            L"ResponseCount",
                            0,
                            &pvarg,
                            0,
                            0);
      if ( !WmiObjectFromPath )
      {
        uiVal = pvarg.uiVal;
        VariantClear(&pvarg);
        v8 = (struct tagHNET_RESPONSE_RANGE *)CoTaskMemAlloc(6 * uiVal);
        *a3 = v8;
        if ( v8 )
          WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v13->lpVtbl->Get)(
                                v13,
                                L"ResponseArray",
                                0,
                                &pvarg,
                                0,
                                0);
        else
          WmiObjectFromPath = -2147024882;
      }
      ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->Release)(v13);
      if ( !WmiObjectFromPath )
      {
        WmiObjectFromPath = SafeArrayAccessData(pvarg.parray, &ppvData);
        if ( !WmiObjectFromPath )
        {
          for ( i = 0; i < (unsigned __int16)uiVal; ++i )
          {
            (***((void (__fastcall ****)(_QWORD, GUID *, struct IWbemClassObject **))ppvData + i))(
              *((_QWORD *)ppvData + i),
              &GUID_dc12a681_737f_11cf_884d_00aa004b2e24,
              &v14);
            WmiObjectFromPath = CopyResponseInstanceToStruct(
                                  v14,
                                  (struct tagHNET_RESPONSE_RANGE *)((char *)*a3 + 6 * i));
            ((void (__fastcall *)(struct IWbemClassObject *))v14->lpVtbl->Release)(v14);
            if ( WmiObjectFromPath < 0 )
              break;
          }
          SafeArrayUnaccessData(pvarg.parray);
        }
        VariantClear(&pvarg);
        if ( !WmiObjectFromPath )
        {
          *a2 = uiVal;
          return (unsigned int)WmiObjectFromPath;
        }
      }
    }
  }
  else
  {
    WmiObjectFromPath = -2147467261;
  }
  if ( *a3 )
  {
    CoTaskMemFree(*a3);
    *a3 = 0;
  }
  return (unsigned int)WmiObjectFromPath;
}

```

## disassembly

```asm
0x180022df0  mov     [rsp-28h+arg_0], rbx
0x180022df5  push    rbp
0x180022df6  push    rsi
0x180022df7  push    rdi
0x180022df8  push    r14
0x180022dfa  push    r15
0x180022dfc  mov     rbp, rsp
0x180022dff  sub     rsp, 60h
0x180022e03  xor     eax, eax
0x180022e05  mov     [rbp+arg_10], 0
0x180022e0d  mov     rbx, rcx
0x180022e10  mov     qword ptr [rbp+pvarg+10h], rax
0x180022e14  xorps   xmm0, xmm0
0x180022e17  mov     [rbp+ppvData], rax
0x180022e1b  lea     rcx, [rbp+pvarg]; pvarg
0x180022e1f  mov     [rbp+arg_18], rax
0x180022e23  movups  xmmword ptr [rbp+pvarg], xmm0
0x180022e27  mov     rdi, r8
0x180022e2a  mov     r15, rdx
0x180022e2d  call    cs:__imp_VariantInit
0x180022e33  test    rdi, rdi
0x180022e36  jz      loc_180022FBD
0x180022e3c  mov     qword ptr [rdi], 0
0x180022e43  test    r15, r15
0x180022e46  jz      loc_180022FA1
0x180022e4c  xor     eax, eax
0x180022e4e  lea     r8, [rbp+arg_10]; struct IWbemClassObject **
0x180022e52  mov     [r15], ax
0x180022e56  mov     rdx, [rbx+48h]; unsigned __int16 *
0x180022e5a  mov     rcx, [rbx+40h]; struct IWbemServices *
0x180022e5e  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180022e63  mov     ebx, eax
0x180022e65  test    eax, eax
0x180022e67  jnz     loc_180022FA6
0x180022e6d  mov     rcx, [rbp+arg_10]
0x180022e71  lea     r9, [rbp+pvarg]
0x180022e75  xor     esi, esi
0x180022e77  lea     rdx, ?c_wszResponseCount@@3QBGB; "ResponseCount"
0x180022e7e  mov     [rsp+60h+var_38], rsi
0x180022e83  xor     r8d, r8d
0x180022e86  mov     [rsp+60h+var_40], rsi
0x180022e8b  mov     rax, [rcx]
0x180022e8e  mov     rax, [rax+20h]
0x180022e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e97  mov     ebx, eax
0x180022e99  test    eax, eax
0x180022e9b  jnz     short loc_180022EF9
0x180022e9d  movzx   esi, word ptr [rbp+pvarg+8]
0x180022ea1  lea     rcx, [rbp+pvarg]; pvarg
0x180022ea5  call    cs:__imp_VariantClear
0x180022eab  lea     rcx, [rsi+rsi*2]
0x180022eaf  add     rcx, rcx; cb
0x180022eb2  call    cs:__imp_CoTaskMemAlloc
0x180022eb8  mov     [rdi], rax
0x180022ebb  test    rax, rax
0x180022ebe  jnz     short loc_180022EC7
0x180022ec0  mov     ebx, 8007000Eh
0x180022ec5  jmp     short loc_180022EF9
0x180022ec7  mov     rcx, [rbp+arg_10]
0x180022ecb  lea     r9, [rbp+pvarg]
0x180022ecf  mov     [rsp+60h+var_38], 0
0x180022ed8  lea     rdx, ?c_wszResponseArray@@3QBGB; "ResponseArray"
0x180022edf  xor     r8d, r8d
0x180022ee2  mov     [rsp+60h+var_40], 0
0x180022eeb  mov     rax, [rcx]
0x180022eee  mov     rax, [rax+20h]
0x180022ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ef7  mov     ebx, eax
0x180022ef9  mov     rcx, [rbp+arg_10]
0x180022efd  mov     rax, [rcx]
0x180022f00  mov     rax, [rax+10h]
0x180022f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f09  test    ebx, ebx
0x180022f0b  jnz     loc_180022FA6
0x180022f11  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x180022f15  lea     rdx, [rbp+ppvData]; ppvData
0x180022f19  call    cs:__imp_SafeArrayAccessData
0x180022f1f  mov     ebx, eax
0x180022f21  test    eax, eax
0x180022f23  jnz     short loc_180022F8D
0x180022f25  xor     r14d, r14d
0x180022f28  cmp     ax, si
0x180022f2b  jnb     short loc_180022F83
0x180022f2d  mov     rax, [rbp+ppvData]
0x180022f31  lea     r8, [rbp+arg_18]
0x180022f35  movzx   ebx, r14w
0x180022f39  lea     rdx, _GUID_dc12a681_737f_11cf_884d_00aa004b2e24
0x180022f40  mov     rcx, [rax+rbx*8]
0x180022f44  mov     rax, [rcx]
0x180022f47  mov     rax, [rax]
0x180022f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f4f  mov     rax, [rdi]
0x180022f52  lea     rcx, [rbx+rbx*2]
0x180022f56  lea     rdx, [rax+rcx*2]; struct tagHNET_RESPONSE_RANGE *
0x180022f5a  mov     rcx, [rbp+arg_18]; struct IWbemClassObject *
0x180022f5e  call    ?CopyResponseInstanceToStruct@@YAJPEAUIWbemClassObject@@PEAUtagHNET_RESPONSE_RANGE@@@Z; CopyResponseInstanceToStruct(IWbemClassObject *,tagHNET_RESPONSE_RANGE *)
0x180022f63  mov     rcx, [rbp+arg_18]
0x180022f67  mov     ebx, eax
0x180022f69  mov     rax, [rcx]
0x180022f6c  mov     rax, [rax+10h]
0x180022f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f75  test    ebx, ebx
0x180022f77  js      short loc_180022F83
0x180022f79  inc     r14w
0x180022f7d  cmp     r14w, si
0x180022f81  jb      short loc_180022F2D
0x180022f83  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x180022f87  call    cs:__imp_SafeArrayUnaccessData
0x180022f8d  lea     rcx, [rbp+pvarg]; pvarg
0x180022f91  call    cs:__imp_VariantClear
0x180022f97  test    ebx, ebx
0x180022f99  jnz     short loc_180022FA6
0x180022f9b  mov     [r15], si
0x180022f9f  jmp     short loc_180022FC2
0x180022fa1  mov     ebx, 80004003h
0x180022fa6  mov     rcx, [rdi]; pv
0x180022fa9  test    rcx, rcx
0x180022fac  jz      short loc_180022FC2
0x180022fae  call    cs:__imp_CoTaskMemFree
0x180022fb4  mov     qword ptr [rdi], 0
0x180022fbb  jmp     short loc_180022FC2
0x180022fbd  mov     ebx, 80004003h
0x180022fc2  mov     eax, ebx
0x180022fc4  mov     rbx, [rsp+60h+arg_0]
0x180022fcc  add     rsp, 60h
0x180022fd0  pop     r15
0x180022fd2  pop     r14
0x180022fd4  pop     rdi
0x180022fd5  pop     rsi
0x180022fd6  pop     rbp
0x180022fd7  retn
```
