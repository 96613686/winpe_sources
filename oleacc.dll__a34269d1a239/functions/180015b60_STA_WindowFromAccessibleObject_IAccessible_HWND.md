# STA_WindowFromAccessibleObject(IAccessible *,HWND__ * *)

- ea: `0x180015b60`
- end: `0x180015d70`
- name: `?STA_WindowFromAccessibleObject@@YAJPEAUIAccessible@@PEAPEAUHWND__@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(struct IAccessible *, HWND *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003b574`

## callees

- `0x180015b60`
- `0x180049010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180015cd3`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180015cd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d52`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015ce9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015ce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015cf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015cf6`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180015c89`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180015c89`

## pseudocode

```c
__int64 __fastcall STA_WindowFromAccessibleObject(IUnknown *a1, HWND *a2)
{
  struct IAccessibleVtbl *lpVtbl; // rax
  int v5; // edi
  LPUNKNOWN v6; // rbx
  struct IUnknownVtbl *v7; // rax
  int v8; // edi
  void *v10; // rax
  void *v11; // rsi
  signed int LastError; // eax
  LPSTREAM ppStm; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v14[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v15; // [rsp+48h] [rbp-30h]
  __int64 v16; // [rsp+80h] [rbp+8h] BYREF
  __int64 v17; // [rsp+90h] [rbp+18h] BYREF
  LPUNKNOWN pUnk; // [rsp+98h] [rbp+20h] BYREF

  lpVtbl = (struct IAccessibleVtbl *)a1->lpVtbl;
  v17 = 0;
  if ( !((unsigned __int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
          a1,
          &IID_IServiceProvider,
          &v17)
    && v17 )
  {
    pUnk = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, LPUNKNOWN *))(*(_QWORD *)v17 + 24LL))(
           v17,
           &IIS_AccWrapBase_GetIUnknown,
           &IID_IAccessible,
           &pUnk);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v6 = pUnk;
    if ( !v5 )
      goto LABEL_4;
    if ( pUnk )
      goto LABEL_5;
  }
  v6 = a1;
  ((void (__fastcall *)(IUnknown *))a1->lpVtbl->AddRef)(a1);
LABEL_4:
  if ( !v6 )
    return 2147549183LL;
LABEL_5:
  v7 = v6->lpVtbl;
  v16 = 0;
  v8 = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))v7->QueryInterface)(v6, &IID_IOleWindow, &v16);
  if ( v8 < 0
    || v16
    && (v8 = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v16 + 24LL))(v16, a2),
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16),
        v8 < 0) )
  {
    if ( v8 == -2147417843 )
    {
      ppStm = 0;
      v8 = CoMarshalInterThreadInterfaceInStream(&IID_IAccessible, v6, &ppStm);
      if ( !v8 )
      {
        v14[0] = ppStm;
        v15 = 0;
        v14[1] = a2;
        LODWORD(v16) = 0;
        v10 = (void *)_o__beginthreadex(0, 0, STA_Thread, v14, 0, &v16);
        v11 = v10;
        if ( v10 )
        {
          WaitForSingleObject(v10, 0xFFFFFFFF);
          v8 = v15;
          CloseHandle(v11);
        }
        else
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
  ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015b60  mov     r11, rsp
0x180015b63  push    rbx
0x180015b64  push    rbp
0x180015b65  push    rsi
0x180015b66  push    rdi
0x180015b67  push    r14
0x180015b69  sub     rsp, 50h
0x180015b6d  mov     rax, [rcx]
0x180015b70  lea     r8, [r11+18h]
0x180015b74  mov     rbp, rdx
0x180015b77  xor     r14d, r14d
0x180015b7a  lea     rdx, IID_IServiceProvider
0x180015b81  mov     [r11+18h], r14
0x180015b85  mov     rsi, rcx
0x180015b88  mov     rax, [rax]
0x180015b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b90  test    eax, eax
0x180015b92  jnz     loc_180015C61
0x180015b98  mov     rcx, [rsp+78h+arg_10]
0x180015ba0  test    rcx, rcx
0x180015ba3  jz      loc_180015C61
0x180015ba9  mov     [rsp+78h+pUnk], r14
0x180015bb1  lea     r9, [rsp+78h+pUnk]
0x180015bb9  mov     rax, [rcx]
0x180015bbc  lea     r8, IID_IAccessible
0x180015bc3  lea     rdx, ?IIS_AccWrapBase_GetIUnknown@@3U_GUID@@A; _GUID IIS_AccWrapBase_GetIUnknown
0x180015bca  mov     rax, [rax+18h]
0x180015bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bd3  mov     rcx, [rsp+78h+arg_10]
0x180015bdb  mov     edi, eax
0x180015bdd  mov     rdx, [rcx]
0x180015be0  mov     rax, [rdx+10h]
0x180015be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015be9  mov     rbx, [rsp+78h+pUnk]
0x180015bf1  test    edi, edi
0x180015bf3  jnz     loc_180015D01
0x180015bf9  test    rbx, rbx
0x180015bfc  jz      short loc_180015C51
0x180015bfe  mov     rax, [rbx]
0x180015c01  lea     r8, [rsp+78h+arg_0]
0x180015c09  lea     rdx, IID_IOleWindow
0x180015c10  mov     [rsp+78h+arg_0], r14
0x180015c18  mov     rcx, rbx
0x180015c1b  mov     rax, [rax]
0x180015c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c23  mov     edi, eax
0x180015c25  test    eax, eax
0x180015c27  jns     loc_180015D0F
0x180015c2d  cmp     edi, 8001010Dh
0x180015c33  jz      short loc_180015C75
0x180015c35  mov     rax, [rbx]
0x180015c38  mov     rcx, rbx
0x180015c3b  mov     rax, [rax+10h]
0x180015c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c44  mov     eax, edi
0x180015c46  add     rsp, 50h
0x180015c4a  pop     r14
0x180015c4c  pop     rdi
0x180015c4d  pop     rsi
0x180015c4e  pop     rbp
0x180015c4f  pop     rbx
0x180015c50  retn
0x180015c51  mov     eax, 8000FFFFh
0x180015c56  add     rsp, 50h
0x180015c5a  pop     r14
0x180015c5c  pop     rdi
0x180015c5d  pop     rsi
0x180015c5e  pop     rbp
0x180015c5f  pop     rbx
0x180015c60  retn
0x180015c61  mov     rax, [rsi]
0x180015c64  mov     rcx, rsi
0x180015c67  mov     rbx, rsi
0x180015c6a  mov     rax, [rax+8]
0x180015c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c73  jmp     short loc_180015BF9
0x180015c75  lea     r8, [rsp+78h+ppStm]; ppStm
0x180015c7a  mov     [rsp+78h+ppStm], r14
0x180015c7f  mov     rdx, rbx; pUnk
0x180015c82  lea     rcx, IID_IAccessible; riid
0x180015c89  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180015c8f  mov     edi, eax
0x180015c91  test    eax, eax
0x180015c93  jnz     short loc_180015C35
0x180015c95  mov     rax, [rsp+78h+ppStm]
0x180015c9a  lea     r9, [rsp+78h+var_40]
0x180015c9f  mov     [rsp+78h+var_40], rax
0x180015ca4  lea     r8, STA_Thread
0x180015cab  lea     rax, [rsp+78h+arg_0]
0x180015cb3  mov     [rsp+78h+var_30], r14
0x180015cb8  mov     [rsp+78h+var_50], rax
0x180015cbd  xor     edx, edx
0x180015cbf  xor     ecx, ecx
0x180015cc1  mov     [rsp+78h+var_58], r14d
0x180015cc6  mov     [rsp+78h+var_38], rbp
0x180015ccb  mov     dword ptr [rsp+78h+arg_0], r14d
0x180015cd3  call    cs:__imp__o__beginthreadex
0x180015cd9  mov     rsi, rax
0x180015cdc  test    rax, rax
0x180015cdf  jz      short loc_180015D52
0x180015ce1  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180015ce6  mov     rcx, rax; hHandle
0x180015ce9  call    cs:__imp_WaitForSingleObject
0x180015cef  mov     edi, dword ptr [rsp+78h+var_30]
0x180015cf3  mov     rcx, rsi; hObject
0x180015cf6  call    cs:__imp_CloseHandle
0x180015cfc  jmp     loc_180015C35
0x180015d01  test    rbx, rbx
0x180015d04  jnz     loc_180015BFE
0x180015d0a  jmp     loc_180015C61
0x180015d0f  mov     rcx, [rsp+78h+arg_0]
0x180015d17  test    rcx, rcx
0x180015d1a  jz      loc_180015C35
0x180015d20  mov     rax, [rcx]
0x180015d23  mov     rdx, rbp
0x180015d26  mov     rax, [rax+18h]
0x180015d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d2f  mov     rcx, [rsp+78h+arg_0]
0x180015d37  mov     edi, eax
0x180015d39  mov     rax, [rcx]
0x180015d3c  mov     rax, [rax+10h]
0x180015d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d45  test    edi, edi
0x180015d47  jns     loc_180015C35
0x180015d4d  jmp     loc_180015C2D
0x180015d52  call    cs:__imp_GetLastError
0x180015d58  mov     edi, eax
0x180015d5a  test    eax, eax
0x180015d5c  jle     loc_180015C35
0x180015d62  movzx   edi, ax
0x180015d65  or      edi, 80070000h
0x180015d6b  jmp     loc_180015C35
```
