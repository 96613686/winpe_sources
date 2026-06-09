# CFindDlg::_ThreadFunc(void *)

- ea: `0x180012ec0`
- end: `0x180012f95`
- name: `?_ThreadFunc@CFindDlg@@CAKPEAX@Z`
- size: `213`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000c004`
- `0x180012ec0`
- `0x180024010`

## import_xrefs

- `USER32!DispatchMessageW` at `0x180012f6a`
- `USER32!DispatchMessageW` at `0x180012f6a`
- `USER32!TranslateMessage` at `0x180012f5f`
- `USER32!TranslateMessage` at `0x180012f5f`
- `USER32!IsDialogMessageW` at `0x180012f50`
- `USER32!IsDialogMessageW` at `0x180012f50`
- `USER32!GetMessageW` at `0x180012f7d`
- `USER32!GetMessageW` at `0x180012f7d`
- `ole32!CoGetInterfaceAndReleaseStream` at `0x180012f07`
- `ole32!CoGetInterfaceAndReleaseStream` at `0x180012f07`
- `ole32!CoInitialize` at `0x180012ecb`
- `ole32!CoInitialize` at `0x180012ecb`
- `ole32!CoUninitialize` at `0x180012f87`
- `ole32!CoUninitialize` at `0x180012f87`

## pseudocode

```c
__int64 __fastcall CFindDlg::_ThreadFunc(_QWORD *Parameter)
{
  HRESULT v2; // eax
  IStream *v3; // rcx
  HRESULT InterfaceAndReleaseStream; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  HWND DialogParamW; // rbx
  tagMSG Msg; // [rsp+30h] [rbp-38h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+8h] BYREF

  v2 = CoInitialize(0);
  v3 = (IStream *)Parameter[4];
  if ( v2 >= 0 )
  {
    ppv = 0;
    InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(v3, &IID_IResultPrshtActions, &ppv);
    Parameter[4] = 0;
    if ( InterfaceAndReleaseStream >= 0 )
    {
      Parameter[5] = ppv;
      DialogParamW = IsolationAwareCreateDialogParamW(v6, v5, v7, v8, (LPARAM)Parameter);
      if ( DialogParamW )
      {
        memset(&Msg, 0, sizeof(Msg));
        while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
        {
          if ( !IsDialogMessageW(DialogParamW, &Msg) )
          {
            TranslateMessage(&Msg);
            DispatchMessageW(&Msg);
          }
        }
      }
    }
    CoUninitialize();
  }
  else
  {
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v3 + 16LL))(v3);
    Parameter[4] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180012ec0  push    rbx
0x180012ec2  sub     rsp, 60h
0x180012ec6  mov     rbx, rcx
0x180012ec9  xor     ecx, ecx; pvReserved
0x180012ecb  call    cs:__imp_CoInitialize
0x180012ed1  mov     rcx, [rbx+20h]; pStm
0x180012ed5  test    eax, eax
0x180012ed7  jns     short loc_180012EF2
0x180012ed9  mov     rax, [rcx]
0x180012edc  mov     rax, [rax+10h]
0x180012ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ee5  mov     qword ptr [rbx+20h], 0
0x180012eed  jmp     loc_180012F8D
0x180012ef2  lea     r8, [rsp+68h+ppv]; ppv
0x180012ef7  mov     [rsp+68h+ppv], 0
0x180012f00  lea     rdx, IID_IResultPrshtActions; iid
0x180012f07  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180012f0d  mov     qword ptr [rbx+20h], 0
0x180012f15  test    eax, eax
0x180012f17  js      short loc_180012F87
0x180012f19  mov     rax, [rsp+68h+ppv]
0x180012f1e  mov     [rbx+28h], rax
0x180012f22  mov     [rsp+68h+var_48], rbx; LPARAM
0x180012f27  call    IsolationAwareCreateDialogParamW
0x180012f2c  mov     rbx, rax
0x180012f2f  test    rax, rax
0x180012f32  jz      short loc_180012F87
0x180012f34  xorps   xmm0, xmm0
0x180012f37  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x180012f3c  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x180012f41  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x180012f46  jmp     short loc_180012F70
0x180012f48  lea     rdx, [rsp+68h+Msg]; lpMsg
0x180012f4d  mov     rcx, rbx; hDlg
0x180012f50  call    cs:__imp_IsDialogMessageW
0x180012f56  test    eax, eax
0x180012f58  jnz     short loc_180012F70
0x180012f5a  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180012f5f  call    cs:__imp_TranslateMessage
0x180012f65  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180012f6a  call    cs:__imp_DispatchMessageW
0x180012f70  xor     r9d, r9d; wMsgFilterMax
0x180012f73  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180012f78  xor     r8d, r8d; wMsgFilterMin
0x180012f7b  xor     edx, edx; hWnd
0x180012f7d  call    cs:__imp_GetMessageW
0x180012f83  test    eax, eax
0x180012f85  jg      short loc_180012F48
0x180012f87  call    cs:__imp_CoUninitialize
0x180012f8d  xor     eax, eax
0x180012f8f  add     rsp, 60h
0x180012f93  pop     rbx
0x180012f94  retn
```
