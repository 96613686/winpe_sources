# DllGetClassObject

- ea: `0x180002860`
- end: `0x180002968`
- name: `DllGetClassObject`
- size: `264`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002860`
- `0x180002970`
- `0x180002a20`
- `0x18000a360`
- `0x18000ab3c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002902`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000289f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000289f`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v5; // rax
  CDimsJobClassFactory *v6; // rax
  struct CModule *v7; // rdx
  CDimsJobClassFactory *v8; // rsi
  unsigned int v9; // edx
  HRESULT v10; // ebx
  HRESULT; // eax
  DWORD LastError; // eax
  signed int v13; // ebx
  __int64 *v14; // rbp
  _QWORD *v15; // rcx
  int *v16; // rbx
  __int64 *v17; // rdx
  __int64 v18; // [rsp+0h] [rbp-38h] BYREF
  signed int pExceptionObject; // [rsp+20h] [rbp-18h] BYREF
  CExcept *v20; // [rsp+28h] [rbp-10h] BYREF
  HRESULT v21; // [rsp+50h] [rbp+18h]

  *ppv = 0;
  v5 = *(_QWORD *)&rclsid->Data1 - 0x4E55AC8558FB76B9LL;
  if ( *(_QWORD *)&rclsid->Data1 == 0x4E55AC8558FB76B9LL )
    v5 = *(_QWORD *)rclsid->Data4 - 0x60D0B193754204ACLL;
  if ( v5 )
  {
     = -2147221231;
    goto LABEL_26;
  }
  v6 = (CDimsJobClassFactory *)LocalAlloc(0, 0x18u);
  if ( !v6 )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10u,
        (__int64)WPP_ea7d1c204d33352b702f4b4b9615bef9_Traceguids,
        LastError);
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    pExceptionObject = v13;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      throw (CExcept *)&pExceptionObject;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &CExcept `RTTI Type Descriptor', &v20) )
      {
        v17 = &v18;
        v14 = v17;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 2) == 0 )
        {
          v16 = (int *)v14[5];
        }
        else
        {
          v16 = (int *)v14[5];
          WPP_SF_D(v15[2], 23u, (__int64)WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids, *v16);
        }
        *((_DWORD *)v14 + 20) = *v16;
         = v21;
        __eh34_try_continuation(0, &CExcept `RTTI Type Descriptor', &loc_18000295F);
LABEL_26:
        ;
      }
    }
  }
  v8 = CDimsJobClassFactory::CDimsJobClassFactory(v6, v7);
  v10 = (**(__int64 (__fastcall ***)(CDimsJobClassFactory *, const IID *const, LPVOID *))v8)(v8, riid, ppv);
  if ( v10 >= 0 )
  {
     = 0;
  }
  else
  {
    CDimsJobClassFactory::`scalar deleting destructor'(v8, v9);
     = v10;
  }
  goto LABEL_26;
}

```

## disassembly

```asm
0x180002860  mov     [rsp+arg_0], rbx
0x180002865  mov     [rsp+arg_8], rsi
0x18000286a  push    rdi
0x18000286b  sub     rsp, 30h
0x18000286f  mov     rbx, r8
0x180002872  mov     rdi, rdx
0x180002875  mov     qword ptr [r8], 0
0x18000287c  mov     rax, [rcx]
0x18000287f  sub     rax, cs:qword_18000DB90
0x180002886  jnz     short loc_180002893
0x180002888  mov     rax, [rcx+8]
0x18000288c  sub     rax, cs:qword_18000DB98
0x180002893  test    rax, rax
0x180002896  jnz     short loc_1800028DB
0x180002898  mov     edx, 18h; uBytes
0x18000289d  xor     ecx, ecx; uFlags
0x18000289f  call    cs:__imp_LocalAlloc
0x1800028a5  test    rax, rax
0x1800028a8  jz      short loc_180002902
0x1800028aa  mov     rcx, rax; this
0x1800028ad  call    ??0CDimsJobClassFactory@@QEAA@AEAVCModule@@@Z; CDimsJobClassFactory::CDimsJobClassFactory(CModule &)
0x1800028b2  mov     rsi, rax
0x1800028b5  mov     rcx, [rax]
0x1800028b8  mov     rax, [rcx]
0x1800028bb  mov     r8, rbx
0x1800028be  mov     rdx, rdi
0x1800028c1  mov     rcx, rsi
0x1800028c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028c9  mov     ebx, eax
0x1800028cb  test    eax, eax
0x1800028cd  jns     short loc_1800028F0
0x1800028cf  mov     rcx, rsi; hMem
0x1800028d2  call    ??_GCDimsJobClassFactory@@QEAAPEAXI@Z; CDimsJobClassFactory::`scalar deleting destructor'(uint)
0x1800028d7  mov     eax, ebx
0x1800028d9  jmp     short loc_1800028E0
0x1800028db  mov     eax, 80040111h
0x1800028e0  mov     rbx, [rsp+38h+arg_0]
0x1800028e5  mov     rsi, [rsp+38h+arg_8]
0x1800028ea  add     rsp, 30h
0x1800028ee  pop     rdi
0x1800028ef  retn
0x1800028f0  xor     eax, eax
0x1800028f2  mov     rbx, [rsp+38h+arg_0]
0x1800028f7  mov     rsi, [rsp+38h+arg_8]
0x1800028fc  add     rsp, 30h
0x180002900  pop     rdi
0x180002901  retn
0x180002902  call    cs:__imp_GetLastError
0x180002908  nop
0x180002909  mov     ebx, eax
0x18000290b  lea     rax, WPP_GLOBAL_Control
0x180002912  mov     rcx, cs:WPP_GLOBAL_Control
0x180002919  cmp     rcx, rax
0x18000291c  jz      short loc_18000293C
0x18000291e  test    byte ptr [rcx+1Ch], 2
0x180002922  jz      short loc_18000293C
0x180002924  mov     edx, 0Ah
0x180002929  mov     r9d, ebx
0x18000292c  lea     r8, WPP_ea7d1c204d33352b702f4b4b9615bef9_Traceguids
0x180002933  mov     rcx, [rcx+10h]
0x180002937  call    WPP_SF_D
0x18000293c  test    ebx, ebx
0x18000293e  jle     short loc_180002949
0x180002940  movzx   ebx, bx
0x180002943  or      ebx, 80070000h
0x180002949  mov     [rsp+38h+pExceptionObject], ebx
0x18000294d  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180002954  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180002959  call    _CxxThrowException_0
0x18000295f  mov     eax, [rsp+38h+arg_10]
0x180002963  jmp     loc_1800028E0
```
