# GetAppFWState(ushort const *,int,long,_APPFIREWALLSTATE *)

- ea: `0x180010fc0`
- end: `0x18001116a`
- name: `?GetAppFWState@@YAJPEBGHJPEAW4_APPFIREWALLSTATE@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(OLECHAR *psz, __int64, __int64, enum _APPFIREWALLSTATE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ccd0`

## callees

- `0x180010fc0`
- `0x180014660`
- `0x1800148c4`
- `0x18001c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180011014`
- `OLEAUT32!__imp_SysAllocString` at `0x180011014`
- `OLEAUT32!__imp_SysFreeString` at `0x180011156`
- `OLEAUT32!__imp_SysFreeString` at `0x180011156`
- `OLEAUT32!__imp_VariantInit` at `0x180010ffb`
- `OLEAUT32!__imp_VariantInit` at `0x180011005`
- `OLEAUT32!__imp_VariantInit` at `0x180010ffb`
- `OLEAUT32!__imp_VariantInit` at `0x180011005`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001106f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001106f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetAppFWState(OLECHAR *psz, __int64 a2, __int64 a3, enum _APPFIREWALLSTATE *a4)
{
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  OLECHAR *v7; // rsi
  HRESULT v8; // ebx
  CEventLogger *v9; // rcx
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  signed int v11; // eax
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  VARIANTARG pvarg; // [rsp+50h] [rbp+7h] BYREF
  VARIANTARG v15; // [rsp+68h] [rbp+1Fh] BYREF
  LPVOID ppv; // [rsp+C8h] [rbp+7Fh] BYREF

  ppv = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v15, 0, sizeof(v15));
  VariantInit(&pvarg);
  VariantInit(&v15);
  *(_DWORD *)a4 = 0;
  v7 = SysAllocString(psz);
  if ( v7 )
  {
    v8 = CoCreateInstance(
           &GUID_304ce942_6e39_40d8_943a_b913c40c9cd4,
           0,
           1u,
           &GUID_f7898af5_cac4_4632_a2ec_da06e5111af2,
           &ppv);
    if ( v8 < 0 )
    {
      CEventLogger::LogEvent(v9, &COM_Problem, L"NetFwMgr");
      CEventLogger::LogError(
        (CEventLogger *)L"GetAppFWState",
        v10,
        L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
        0x243u,
        L"GetAppFWState",
        v8);
      goto LABEL_16;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64, __int64, _QWORD, int, VARIANTARG *, VARIANTARG *))(*(_QWORD *)ppv + 80LL))(
            ppv,
            v7,
            2,
            52341,
            0,
            6,
            &pvarg,
            &v15);
    v8 = v11;
    if ( v11 < 0 )
    {
      CEventLogger::LogError(
        (CEventLogger *)L"GetAppFWState",
        v12,
        L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
        0x24Fu,
        L"GetAppFWState",
        v11);
      goto LABEL_16;
    }
    if ( pvarg.vt == 11 && v15.vt == 11 )
    {
      if ( pvarg.iVal == -1 )
      {
        if ( !v15.iVal )
        {
          *(_DWORD *)a4 = 1;
          goto LABEL_16;
        }
      }
      else if ( !pvarg.iVal )
      {
        *(_DWORD *)a4 = 2;
        goto LABEL_16;
      }
      *(_DWORD *)a4 = 3;
    }
  }
  else
  {
    v8 = -2147024882;
    CEventLogger::LogError(
      (CEventLogger *)L"GetAppFWState",
      v6,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x236u,
      L"GetAppFWState",
      0x8007000E);
  }
LABEL_16:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v7 )
    SysFreeString(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010fc0  push    rbp
0x180010fc2  push    rbx
0x180010fc3  push    rsi
0x180010fc4  push    rdi
0x180010fc5  lea     rbp, [rsp-3Fh]
0x180010fca  sub     rsp, 88h
0x180010fd1  xor     eax, eax
0x180010fd3  mov     [rbp+57h+arg_18], 0
0x180010fdb  mov     rbx, rcx
0x180010fde  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180010fe2  xorps   xmm0, xmm0
0x180010fe5  mov     qword ptr [rbp+57h+var_38+10h], rax
0x180010fe9  xorps   xmm1, xmm1
0x180010fec  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180010ff0  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180010ff4  mov     rdi, r9
0x180010ff7  movups  xmmword ptr [rbp+57h+var_38], xmm1
0x180010ffb  call    cs:__imp_VariantInit
0x180011001  lea     rcx, [rbp+57h+var_38]; pvarg
0x180011005  call    cs:__imp_VariantInit
0x18001100b  mov     rcx, rbx; psz
0x18001100e  mov     dword ptr [rdi], 0
0x180011014  call    cs:__imp_SysAllocString
0x18001101a  mov     rsi, rax
0x18001101d  test    rax, rax
0x180011020  jnz     short loc_180011052
0x180011022  mov     ebx, 8007000Eh
0x180011027  mov     [rsp+0A0h+var_78], 8007000Eh; unsigned int
0x18001102f  mov     r9d, 236h; unsigned int
0x180011035  lea     rcx, aGetappfwstate; "GetAppFWState"
0x18001103c  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180011043  mov     [rsp+0A0h+ppv], rcx; unsigned __int16 *
0x180011048  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18001104d  jmp     loc_180011131
0x180011052  xor     edx, edx; pUnkOuter
0x180011054  lea     rax, [rbp+57h+arg_18]
0x180011058  lea     r9, _GUID_f7898af5_cac4_4632_a2ec_da06e5111af2; riid
0x18001105f  mov     [rsp+0A0h+ppv], rax; ppv
0x180011064  lea     rcx, _GUID_304ce942_6e39_40d8_943a_b913c40c9cd4; rclsid
0x18001106b  lea     r8d, [rdx+1]; dwClsContext
0x18001106f  call    cs:__imp_CoCreateInstance
0x180011075  mov     ebx, eax
0x180011077  test    eax, eax
0x180011079  jns     short loc_18001109A
0x18001107b  lea     r8, aNetfwmgr; "NetFwMgr"
0x180011082  lea     rdx, COM_Problem; struct _EVENT_DESCRIPTOR *
0x180011089  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x18001108e  mov     r9d, 243h
0x180011094  mov     [rsp+0A0h+var_78], ebx
0x180011098  jmp     short loc_180011035
0x18001109a  mov     rcx, [rbp+57h+arg_18]
0x18001109e  lea     rdx, [rbp+57h+var_38]
0x1800110a2  mov     [rsp+0A0h+var_68], rdx
0x1800110a7  mov     r9d, 0CC75h
0x1800110ad  lea     rdx, [rbp+57h+pvarg]
0x1800110b1  mov     r8d, 2
0x1800110b7  mov     [rsp+0A0h+var_70], rdx
0x1800110bc  mov     rdx, rsi
0x1800110bf  mov     rax, [rcx]
0x1800110c2  mov     [rsp+0A0h+var_78], 6
0x1800110ca  mov     [rsp+0A0h+ppv], 0
0x1800110d3  mov     rax, [rax+50h]
0x1800110d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110dc  mov     ebx, eax
0x1800110de  test    eax, eax
0x1800110e0  jns     short loc_1800110F1
0x1800110e2  mov     [rsp+0A0h+var_78], eax
0x1800110e6  mov     r9d, 24Fh
0x1800110ec  jmp     loc_180011035
0x1800110f1  mov     eax, 0Bh
0x1800110f6  cmp     ax, word ptr [rbp+57h+pvarg]
0x1800110fa  jnz     short loc_180011131
0x1800110fc  cmp     ax, word ptr [rbp+57h+var_38]
0x180011100  jnz     short loc_180011131
0x180011102  or      eax, 0FFFFFFFFh
0x180011105  cmp     ax, word ptr [rbp+57h+pvarg+8]
0x180011109  jnz     short loc_18001111B
0x18001110b  xor     eax, eax
0x18001110d  cmp     ax, word ptr [rbp+57h+var_38+8]
0x180011111  jnz     short loc_18001112B
0x180011113  mov     dword ptr [rdi], 1
0x180011119  jmp     short loc_180011131
0x18001111b  xor     eax, eax
0x18001111d  cmp     ax, word ptr [rbp+57h+pvarg+8]
0x180011121  jnz     short loc_18001112B
0x180011123  mov     dword ptr [rdi], 2
0x180011129  jmp     short loc_180011131
0x18001112b  mov     dword ptr [rdi], 3
0x180011131  mov     rcx, [rbp+57h+arg_18]
0x180011135  test    rcx, rcx
0x180011138  jz      short loc_18001114E
0x18001113a  mov     rax, [rcx]
0x18001113d  mov     rax, [rax+10h]
0x180011141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011146  mov     [rbp+57h+arg_18], 0
0x18001114e  test    rsi, rsi
0x180011151  jz      short loc_18001115C
0x180011153  mov     rcx, rsi; bstrString
0x180011156  call    cs:__imp_SysFreeString
0x18001115c  mov     eax, ebx
0x18001115e  add     rsp, 88h
0x180011165  pop     rdi
0x180011166  pop     rsi
0x180011167  pop     rbx
0x180011168  pop     rbp
0x180011169  retn
```
