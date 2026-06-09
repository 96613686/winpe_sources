# CRASHookPage::OnReset(void)

- ea: `0x18001ecb0`
- end: `0x18001ee80`
- name: `?OnReset@CRASHookPage@@UEAAJXZ`
- size: `464`
- prototype: `__int64 __fastcall(CRASHookPage *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001ecb0`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001ecf0`
- `rtutils!TracePrintfExA` at `0x18001ed64`
- `rtutils!TracePrintfExA` at `0x18001ed9d`
- `rtutils!TracePrintfExA` at `0x18001edee`
- `rtutils!TracePrintfExA` at `0x18001ee26`
- `rtutils!TracePrintfExA` at `0x18001ecf0`
- `rtutils!TracePrintfExA` at `0x18001ed64`
- `rtutils!TracePrintfExA` at `0x18001ed9d`
- `rtutils!TracePrintfExA` at `0x18001edee`
- `rtutils!TracePrintfExA` at `0x18001ee26`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ed20`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ed20`

## string_xrefs

- `0x18001ed93`: `CRASHookPage::OnReset:Failed to do CoCreateInstance for IID_IGlobalInterfaceTable. hr = %#x`
- `0x18001ee1c`: `CRASHookPage::OnReset:DeleteRASEntry result. hr = %#x`

## pseudocode

```c
__int64 __fastcall CRASHookPage::OnReset(CRASHookPage *this)
{
  int v1; // edi
  HRESULT v3; // eax
  int v4; // eax
  __int64 v5; // rcx
  int v6; // eax
  int v7; // eax
  __int64 v8; // rax
  __int64 v10; // [rsp+50h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+28h] BYREF

  v1 = 0;
  v10 = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "CRASHookPage::OnReset.");
  if ( *((_DWORD *)this + 12) )
  {
    ppv = 0;
    v3 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &ppv);
    if ( v3 < 0 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "CRASHookPage::OnReset:Failed to do CoCreateInstance for IID_IGlobalInterfaceTable. hr = %#x",
          v3);
    }
    else
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 40LL))(
             ppv,
             *((unsigned int *)this + 12),
             &IID_IRasGcwLUA,
             &v10);
      if ( v4 < 0 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "CRASHookPage::OnReset:GetInterfaceFromGlobal failed for IRasGcwLUA. hr = %#x",
            v4);
        v10 = 0;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      v1 = 1;
    }
    v5 = v10;
  }
  else
  {
    v5 = *((_QWORD *)this + 8);
    v10 = v5;
  }
  if ( v5 )
  {
    if ( *((_DWORD *)this + 19) )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v5 + 48LL))(v5, *((_QWORD *)this + 7), 1);
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "CRASHookPage::OnReset:SetRASCredentials result. hr = %#x", v6);
      v5 = v10;
    }
    if ( *((_DWORD *)this + 18) )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 32LL))(v5, *((_QWORD *)this + 7));
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "CRASHookPage::OnReset:DeleteRASEntry result. hr = %#x", v7);
      (*(void (__fastcall **)(CRASHookPage *))(*(_QWORD *)this + 104LL))(this);
    }
  }
  v8 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 9) = 0;
  *(_DWORD *)(v8 + 4952) = 0;
  if ( v1 && v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return 0;
}

```

## disassembly

```asm
0x18001ecb0  mov     [rsp-18h+arg_10], rbx
0x18001ecb5  mov     [rsp-18h+arg_18], rdi
0x18001ecba  push    rbp
0x18001ecbb  push    r14
0x18001ecbd  push    r15
0x18001ecbf  mov     rbp, rsp
0x18001ecc2  sub     rsp, 30h
0x18001ecc6  xor     edi, edi
0x18001ecc8  mov     [rbp+arg_0], 0
0x18001ecd0  mov     rbx, rcx
0x18001ecd3  or      r14d, 0FFFFFFFFh
0x18001ecd7  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001ecdd  lea     r15d, [rdi+0Ch]
0x18001ece1  cmp     ecx, r14d
0x18001ece4  jz      short loc_18001ECF6
0x18001ece6  lea     r8, aCrashookpageOn_22; "CRASHookPage::OnReset."
0x18001eced  mov     edx, r15d; dwFlags
0x18001ecf0  call    cs:__imp_TracePrintfExA
0x18001ecf6  cmp     [rbx+30h], edi
0x18001ecf9  jz      loc_18001EDA9
0x18001ecff  xor     edx, edx; pUnkOuter
0x18001ed01  mov     [rbp+arg_8], rdi
0x18001ed05  lea     rax, [rbp+arg_8]
0x18001ed09  lea     r9, IID_IGlobalInterfaceTable; riid
0x18001ed10  mov     [rsp+30h+ppv], rax; ppv
0x18001ed15  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001ed1c  lea     r8d, [rdx+1]; dwClsContext
0x18001ed20  call    cs:__imp_CoCreateInstance
0x18001ed26  test    eax, eax
0x18001ed28  js      short loc_18001ED85
0x18001ed2a  mov     rcx, [rbp+arg_8]
0x18001ed2e  lea     r9, [rbp+arg_0]
0x18001ed32  mov     edx, [rbx+30h]
0x18001ed35  lea     r8, IID_IRasGcwLUA
0x18001ed3c  mov     rax, [rcx]
0x18001ed3f  mov     rax, [rax+28h]
0x18001ed43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed48  test    eax, eax
0x18001ed4a  jns     short loc_18001ED6E
0x18001ed4c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001ed52  cmp     ecx, r14d
0x18001ed55  jz      short loc_18001ED6A
0x18001ed57  mov     r9d, eax
0x18001ed5a  lea     r8, aCrashookpageOn_21; "CRASHookPage::OnReset:GetInterfaceFromG"...
0x18001ed61  mov     edx, r15d; dwFlags
0x18001ed64  call    cs:__imp_TracePrintfExA
0x18001ed6a  mov     [rbp+arg_0], rdi
0x18001ed6e  mov     rcx, [rbp+arg_8]
0x18001ed72  mov     rax, [rcx]
0x18001ed75  mov     rax, [rax+10h]
0x18001ed79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed7e  mov     edi, 1
0x18001ed83  jmp     short loc_18001EDA3
0x18001ed85  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001ed8b  cmp     ecx, r14d
0x18001ed8e  jz      short loc_18001EDA3
0x18001ed90  mov     r9d, eax
0x18001ed93  lea     r8, aCrashookpageOn_0; "CRASHookPage::OnReset:Failed to do CoCr"...
0x18001ed9a  mov     edx, r15d; dwFlags
0x18001ed9d  call    cs:__imp_TracePrintfExA
0x18001eda3  mov     rcx, [rbp+arg_0]
0x18001eda7  jmp     short loc_18001EDB1
0x18001eda9  mov     rcx, [rbx+40h]
0x18001edad  mov     [rbp+arg_0], rcx
0x18001edb1  test    rcx, rcx
0x18001edb4  jz      loc_18001EE3B
0x18001edba  cmp     dword ptr [rbx+4Ch], 0
0x18001edbe  jz      short loc_18001EDF8
0x18001edc0  mov     rax, [rcx]
0x18001edc3  mov     r8d, 1
0x18001edc9  mov     rdx, [rbx+38h]
0x18001edcd  mov     rax, [rax+30h]
0x18001edd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edd6  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001eddc  cmp     ecx, r14d
0x18001eddf  jz      short loc_18001EDF4
0x18001ede1  mov     r9d, eax
0x18001ede4  lea     r8, aCrashookpageOn_13; "CRASHookPage::OnReset:SetRASCredentials"...
0x18001edeb  mov     edx, r15d; dwFlags
0x18001edee  call    cs:__imp_TracePrintfExA
0x18001edf4  mov     rcx, [rbp+arg_0]
0x18001edf8  cmp     dword ptr [rbx+48h], 0
0x18001edfc  jz      short loc_18001EE3B
0x18001edfe  mov     rax, [rcx]
0x18001ee01  mov     rdx, [rbx+38h]
0x18001ee05  mov     rax, [rax+20h]
0x18001ee09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee0e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001ee14  cmp     ecx, r14d
0x18001ee17  jz      short loc_18001EE2C
0x18001ee19  mov     r9d, eax
0x18001ee1c  lea     r8, aCrashookpageOn_3; "CRASHookPage::OnReset:DeleteRASEntry re"...
0x18001ee23  mov     edx, r15d; dwFlags
0x18001ee26  call    cs:__imp_TracePrintfExA
0x18001ee2c  mov     rax, [rbx]
0x18001ee2f  mov     rcx, rbx
0x18001ee32  mov     rax, [rax+68h]
0x18001ee36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee3b  mov     rax, [rbx+38h]
0x18001ee3f  mov     qword ptr [rbx+48h], 0
0x18001ee47  mov     dword ptr [rax+1358h], 0
0x18001ee51  test    edi, edi
0x18001ee53  jz      short loc_18001EE6A
0x18001ee55  mov     rcx, [rbp+arg_0]
0x18001ee59  test    rcx, rcx
0x18001ee5c  jz      short loc_18001EE6A
0x18001ee5e  mov     rax, [rcx]
0x18001ee61  mov     rax, [rax+10h]
0x18001ee65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee6a  mov     rbx, [rsp+30h+arg_10]
0x18001ee6f  xor     eax, eax
0x18001ee71  mov     rdi, [rsp+30h+arg_18]
0x18001ee76  add     rsp, 30h
0x18001ee7a  pop     r15
0x18001ee7c  pop     r14
0x18001ee7e  pop     rbp
0x18001ee7f  retn
```
