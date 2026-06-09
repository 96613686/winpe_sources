# CHNetConn::GetName(ushort * *)

- ea: `0x18001c9f0`
- end: `0x18001cd3c`
- name: `?GetName@CHNetConn@@UEAAJPEAPEAG@Z`
- size: `844`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001f26`
- `0x18000a45c`
- `0x18000a484`
- `0x18001b110`
- `0x18001c9f0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cc76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cc76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ca6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ca6b`
- `OLEAUT32!__imp_SysAllocString` at `0x18001cbbb`
- `OLEAUT32!__imp_SysAllocString` at `0x18001cbbb`
- `OLEAUT32!__imp_VariantClear` at `0x18001cbf3`
- `OLEAUT32!__imp_VariantClear` at `0x18001cbf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cc4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cc4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cb3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cb46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cb3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cb46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc84`

## pseudocode

```c
__int64 __fastcall CHNetConn::GetName(CHNetConn *this, unsigned __int16 **a2)
{
  PVOID *v4; // rcx
  unsigned __int16 *v5; // r14
  int v6; // eax
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  LPVOID *v11; // rcx
  unsigned __int16 *v12; // rax
  int v13; // ecx
  int v14; // edx
  const OLECHAR *v15; // rcx
  int v16; // ebx
  __int64 v17; // rax
  SIZE_T v18; // rbx
  unsigned __int16 *v19; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  struct IWbemClassObject *v22; // [rsp+98h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v24; // [rsp+A8h] [rbp+58h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v24 = 0;
  pv = 0;
  if ( a2 )
  {
    *a2 = 0;
    v5 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v6 = (*(__int64 (__fastcall **)(CHNetConn *, __int64 *))(*(_QWORD *)this + 24LL))(this, &v24);
    v7 = v6;
    if ( v6 >= 0 )
    {
      if ( v6 )
        goto LABEL_34;
      v7 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v24 + 56LL))(v24, &pv);
      if ( (v7 & 0x80000000) == 0 )
      {
        v11 = (LPVOID *)pv;
        v5 = (unsigned __int16 *)*((_QWORD *)this + 14);
        *((_QWORD *)this + 14) = *((_QWORD *)pv + 2);
        CoTaskMemFree(v11[3]);
        CoTaskMemFree(pv);
        v7 = 0;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v7);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      if ( v7 )
        goto LABEL_34;
      if ( !v5 )
        goto LABEL_52;
      v12 = v5;
      do
      {
        v13 = *(unsigned __int16 *)((char *)v12 + *((_QWORD *)this + 14) - (_QWORD)v5);
        v14 = *v12 - v13;
        if ( v14 )
          break;
        ++v12;
      }
      while ( v13 );
      if ( v14 )
      {
LABEL_52:
        v22 = 0;
        memset(&pvarg, 0, sizeof(pvarg));
        if ( !CHNetConn::GetConnectionObject(this, &v22) )
        {
          v15 = (const OLECHAR *)*((_QWORD *)this + 14);
          pvarg.vt = 8;
          pvarg.llVal = (LONGLONG)SysAllocString(v15);
          if ( pvarg.llVal )
          {
            v16 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v22->lpVtbl->Put)(
                    v22,
                    L"Name",
                    0,
                    &pvarg,
                    0);
            VariantClear(&pvarg);
            if ( !v16 )
              (*(void (__fastcall **)(_QWORD, struct IWbemClassObject *, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 8)
                                                                                                 + 112LL))(
                *((_QWORD *)this + 8),
                v22,
                1,
                0,
                0);
          }
          ((void (__fastcall *)(struct IWbemClassObject *))v22->lpVtbl->Release)(v22);
        }
      }
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)(*((_QWORD *)this + 14) + 2 * v17) );
      v18 = (unsigned int)(2 * v17 + 2);
      v19 = (unsigned __int16 *)CoTaskMemAlloc(v18);
      *a2 = v19;
      if ( v19 )
      {
        memcpy_0(v19, *((const void **)this + 14), (unsigned int)v18);
      }
      else
      {
        v7 = -2147024882;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 60;
          v10 = 2147942414LL;
          goto LABEL_11;
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 58;
        v10 = (unsigned int)v6;
LABEL_11:
        WPP_SF_d(v8[2], v9, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v10);
      }
    }
LABEL_34:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( v5 )
      CoTaskMemFree(v5);
    goto LABEL_44;
  }
  v7 = -2147467261;
  if ( v4 == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
  {
    WPP_SF_d(v4[2], 57, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, 2147500035LL);
LABEL_44:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 61, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18001c9f0  mov     [rsp-38h+arg_0], rbx
0x18001c9f5  push    rbp
0x18001c9f6  push    rsi
0x18001c9f7  push    rdi
0x18001c9f8  push    r12
0x18001c9fa  push    r13
0x18001c9fc  push    r14
0x18001c9fe  push    r15
0x18001ca00  mov     rbp, rsp
0x18001ca03  sub     rsp, 50h
0x18001ca07  mov     r15, rdx
0x18001ca0a  mov     rsi, rcx
0x18001ca0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca14  lea     rdi, WPP_GLOBAL_Control
0x18001ca1b  mov     ebx, 8
0x18001ca20  cmp     rcx, rdi
0x18001ca23  jz      short loc_18001CA4A
0x18001ca25  test    [rcx+1Ch], bl
0x18001ca28  jz      short loc_18001CA4A
0x18001ca2a  cmp     byte ptr [rcx+19h], 6
0x18001ca2e  jb      short loc_18001CA4A
0x18001ca30  mov     rcx, [rcx+10h]
0x18001ca34  lea     edx, [rbx+30h]
0x18001ca37  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001ca3e  call    WPP_SF_
0x18001ca43  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca4a  xor     r13d, r13d
0x18001ca4d  mov     [rbp+arg_18], r13
0x18001ca51  mov     [rbp+pv], r13
0x18001ca55  test    r15, r15
0x18001ca58  jz      loc_18001CCBF
0x18001ca5e  lea     r12, [rsi+10h]
0x18001ca62  mov     [r15], r13
0x18001ca65  mov     rcx, r12; lpCriticalSection
0x18001ca68  mov     r14d, r13d
0x18001ca6b  call    cs:__imp_EnterCriticalSection
0x18001ca71  mov     rax, [rsi]
0x18001ca74  lea     rdx, [rbp+arg_18]
0x18001ca78  mov     rcx, rsi
0x18001ca7b  mov     rax, [rax+18h]
0x18001ca7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca84  mov     edi, eax
0x18001ca86  test    eax, eax
0x18001ca88  jns     short loc_18001CAD0
0x18001ca8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca91  lea     rsi, WPP_GLOBAL_Control
0x18001ca98  cmp     rcx, rsi
0x18001ca9b  jz      loc_18001CC73
0x18001caa1  test    [rcx+1Ch], bl
0x18001caa4  jz      loc_18001CC73
0x18001caaa  cmp     byte ptr [rcx+19h], 2
0x18001caae  jb      loc_18001CC73
0x18001cab4  lea     edx, [r13+3Ah]
0x18001cab8  mov     r9d, eax
0x18001cabb  mov     rcx, [rcx+10h]
0x18001cabf  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001cac6  call    WPP_SF_d
0x18001cacb  jmp     loc_18001CC73
0x18001cad0  jnz     loc_18001CC6C
0x18001cad6  mov     rcx, [rbp+arg_18]
0x18001cada  lea     rdx, [rbp+pv]
0x18001cade  mov     rax, [rcx]
0x18001cae1  mov     rax, [rax+38h]
0x18001cae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caea  mov     edi, eax
0x18001caec  test    eax, eax
0x18001caee  jns     short loc_18001CB28
0x18001caf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001caf7  lea     rax, WPP_GLOBAL_Control
0x18001cafe  cmp     rcx, rax
0x18001cb01  jz      short loc_18001CB4F
0x18001cb03  test    [rcx+1Ch], bl
0x18001cb06  jz      short loc_18001CB4F
0x18001cb08  cmp     byte ptr [rcx+19h], 2
0x18001cb0c  jb      short loc_18001CB4F
0x18001cb0e  mov     rcx, [rcx+10h]
0x18001cb12  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001cb19  mov     edx, 3Bh ; ';'
0x18001cb1e  mov     r9d, edi
0x18001cb21  call    WPP_SF_d
0x18001cb26  jmp     short loc_18001CB4F
0x18001cb28  mov     rcx, [rbp+pv]
0x18001cb2c  mov     r14, [rsi+70h]
0x18001cb30  mov     rax, [rcx+10h]
0x18001cb34  mov     [rsi+70h], rax
0x18001cb38  mov     rcx, [rcx+18h]; pv
0x18001cb3c  call    cs:__imp_CoTaskMemFree
0x18001cb42  mov     rcx, [rbp+pv]; pv
0x18001cb46  call    cs:__imp_CoTaskMemFree
0x18001cb4c  mov     edi, r13d
0x18001cb4f  mov     rcx, [rbp+arg_18]
0x18001cb53  mov     rax, [rcx]
0x18001cb56  mov     rax, [rax+10h]
0x18001cb5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb5f  test    edi, edi
0x18001cb61  jnz     loc_18001CC6C
0x18001cb67  test    r14, r14
0x18001cb6a  jz      short loc_18001CB92
0x18001cb6c  mov     r8, [rsi+70h]
0x18001cb70  mov     rax, r14
0x18001cb73  sub     r8, r14
0x18001cb76  movzx   edx, word ptr [rax]
0x18001cb79  movzx   ecx, word ptr [rax+r8]
0x18001cb7e  sub     edx, ecx
0x18001cb80  jnz     short loc_18001CB8A
0x18001cb82  add     rax, 2
0x18001cb86  test    ecx, ecx
0x18001cb88  jnz     short loc_18001CB76
0x18001cb8a  test    edx, edx
0x18001cb8c  jz      loc_18001CC2D
0x18001cb92  xorps   xmm0, xmm0
0x18001cb95  mov     [rbp+arg_8], r13
0x18001cb99  xor     eax, eax
0x18001cb9b  lea     rdx, [rbp+arg_8]; struct IWbemClassObject **
0x18001cb9f  mov     rcx, rsi; this
0x18001cba2  mov     qword ptr [rbp+pvarg+10h], rax
0x18001cba6  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001cbaa  call    ?GetConnectionObject@CHNetConn@@IEAAJPEAPEAUIWbemClassObject@@@Z; CHNetConn::GetConnectionObject(IWbemClassObject * *)
0x18001cbaf  test    eax, eax
0x18001cbb1  jnz     short loc_18001CC2D
0x18001cbb3  mov     rcx, [rsi+70h]; psz
0x18001cbb7  mov     word ptr [rbp+pvarg], bx
0x18001cbbb  call    cs:__imp_SysAllocString
0x18001cbc1  mov     qword ptr [rbp+pvarg+8], rax
0x18001cbc5  test    rax, rax
0x18001cbc8  jz      short loc_18001CC1D
0x18001cbca  mov     rcx, [rbp+arg_8]
0x18001cbce  lea     r9, [rbp+pvarg]
0x18001cbd2  xor     r8d, r8d
0x18001cbd5  mov     dword ptr [rsp+50h+var_30], r13d
0x18001cbda  lea     rdx, ?c_wszName@@3QBGB; "Name"
0x18001cbe1  mov     rax, [rcx]
0x18001cbe4  mov     rax, [rax+28h]
0x18001cbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbed  lea     rcx, [rbp+pvarg]; pvarg
0x18001cbf1  mov     ebx, eax
0x18001cbf3  call    cs:__imp_VariantClear
0x18001cbf9  test    ebx, ebx
0x18001cbfb  jnz     short loc_18001CC1D
0x18001cbfd  mov     rcx, [rsi+40h]
0x18001cc01  lea     r8d, [rbx+1]
0x18001cc05  mov     rdx, [rbp+arg_8]
0x18001cc09  xor     r9d, r9d
0x18001cc0c  mov     [rsp+50h+var_30], r13
0x18001cc11  mov     rax, [rcx]
0x18001cc14  mov     rax, [rax+70h]
0x18001cc18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc1d  mov     rcx, [rbp+arg_8]
0x18001cc21  mov     rax, [rcx]
0x18001cc24  mov     rax, [rax+10h]
0x18001cc28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc2d  mov     rcx, [rsi+70h]
0x18001cc31  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001cc35  inc     rax
0x18001cc38  cmp     [rcx+rax*2], r13w
0x18001cc3d  jnz     short loc_18001CC35
0x18001cc3f  lea     eax, ds:2[rax*2]
0x18001cc46  mov     ecx, eax; cb
0x18001cc48  mov     ebx, eax
0x18001cc4a  call    cs:__imp_CoTaskMemAlloc
0x18001cc50  mov     [r15], rax
0x18001cc53  test    rax, rax
0x18001cc56  jz      short loc_18001CC8C
0x18001cc58  mov     rdx, [rsi+70h]; Src
0x18001cc5c  mov     r8d, ebx; Size
0x18001cc5f  mov     rcx, rax; void *
0x18001cc62  call    memcpy_0
0x18001cc67  mov     ebx, 8
0x18001cc6c  lea     rsi, WPP_GLOBAL_Control
0x18001cc73  mov     rcx, r12; lpCriticalSection
0x18001cc76  call    cs:__imp_LeaveCriticalSection
0x18001cc7c  test    r14, r14
0x18001cc7f  jz      short loc_18001CCF3
0x18001cc81  mov     rcx, r14; pv
0x18001cc84  call    cs:__imp_CoTaskMemFree
0x18001cc8a  jmp     short loc_18001CCF3
0x18001cc8c  mov     edi, 8007000Eh
0x18001cc91  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc98  lea     rsi, WPP_GLOBAL_Control
0x18001cc9f  mov     ebx, 8
0x18001cca4  cmp     rcx, rsi
0x18001cca7  jz      short loc_18001CC73
0x18001cca9  test    [rcx+1Ch], bl
0x18001ccac  jz      short loc_18001CC73
0x18001ccae  cmp     byte ptr [rcx+19h], 2
0x18001ccb2  jb      short loc_18001CC73
0x18001ccb4  lea     edx, [rbx+34h]
0x18001ccb7  mov     r9d, edi
0x18001ccba  jmp     loc_18001CABB
0x18001ccbf  mov     edi, 80004003h
0x18001ccc4  lea     rsi, WPP_GLOBAL_Control
0x18001cccb  cmp     rcx, rsi
0x18001ccce  jz      short loc_18001CD22
0x18001ccd0  test    [rcx+1Ch], bl
0x18001ccd3  jz      short loc_18001CCFA
0x18001ccd5  cmp     byte ptr [rcx+19h], 2
0x18001ccd9  jb      short loc_18001CCFA
0x18001ccdb  mov     rcx, [rcx+10h]
0x18001ccdf  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001cce6  mov     edx, 39h ; '9'
0x18001cceb  mov     r9d, edi
0x18001ccee  call    WPP_SF_d
0x18001ccf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccfa  cmp     rcx, rsi
0x18001ccfd  jz      short loc_18001CD22
0x18001ccff  test    [rcx+1Ch], bl
0x18001cd02  jz      short loc_18001CD22
0x18001cd04  cmp     byte ptr [rcx+19h], 6
0x18001cd08  jb      short loc_18001CD22
0x18001cd0a  mov     rcx, [rcx+10h]
0x18001cd0e  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001cd15  mov     edx, 3Dh ; '='
0x18001cd1a  mov     r9d, edi
0x18001cd1d  call    WPP_SF_d
0x18001cd22  mov     rbx, [rsp+50h+arg_0]
0x18001cd2a  mov     eax, edi
0x18001cd2c  add     rsp, 50h
0x18001cd30  pop     r15
0x18001cd32  pop     r14
0x18001cd34  pop     r13
0x18001cd36  pop     r12
0x18001cd38  pop     rdi
0x18001cd39  pop     rsi
0x18001cd3a  pop     rbp
0x18001cd3b  retn
```
