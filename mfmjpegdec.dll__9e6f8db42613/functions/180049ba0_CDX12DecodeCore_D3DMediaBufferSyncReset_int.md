# CDX12DecodeCore::D3DMediaBufferSyncReset(int *)

- ea: `0x180049ba0`
- end: `0x180049d13`
- name: `?D3DMediaBufferSyncReset@CDX12DecodeCore@@UEAAJPEAH@Z`
- size: `371`
- prototype: `__int64 __fastcall(CDX12DecodeCore *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040000`

## callees

- `0x18003f138`
- `0x180049ba0`
- `0x18004a11c`
- `0x18004ab40`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049bc2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049bc2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180049c96`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180049c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049bdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049bdb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDX12DecodeCore::D3DMediaBufferSyncReset(CDX12DecodeCore *this, unsigned int *a2)
{
  HANDLE EventW; // rbx
  signed int LastError; // eax
  unsigned int v6; // edi
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF
  HANDLE v11; // [rsp+68h] [rbp+20h] BYREF

  EventW = CreateEventW(0, 0, 0, 0);
  v11 = EventW;
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_5;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( !v6 )
  {
LABEL_5:
    v10 = 0;
    if ( g_wppLevels )
      WPP_SF_dqq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        &WPP_658c79110f173b2f2946ffe2569864d0_Traceguids,
        *a2,
        *(_QWORD *)(*((_QWORD *)this + 13) + 8LL * (int)*a2),
        this);
    v7 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)this + 13) + 8LL * (int)*a2);
    v8 = **v7;
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v10);
    v6 = v8(v7, &GUID_802302b0_82de_45e1_b421_f19ee5bdaf23, &v10);
    if ( !v6 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, HANDLE))(*(_QWORD *)v10 + 24LL))(v10, EventW);
      if ( !v6 )
      {
        WaitForSingleObject(EventW, 0xFFFFFFFF);
        if ( g_wppLevels )
          WPP_SF_dqq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v6 + 25,
            &WPP_658c79110f173b2f2946ffe2569864d0_Traceguids,
            *a2,
            *(_QWORD *)(*((_QWORD *)this + 13) + 8LL * (int)*a2),
            this);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10);
      }
    }
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v10);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
  return v6;
}

```

## disassembly

```asm
0x180049ba0  mov     [rsp+arg_0], rbx
0x180049ba5  mov     [rsp+arg_8], rbp
0x180049baa  push    rsi
0x180049bab  push    rdi
0x180049bac  push    r14
0x180049bae  sub     rsp, 30h
0x180049bb2  mov     r14, rdx
0x180049bb5  mov     rbp, rcx
0x180049bb8  xor     r9d, r9d; lpName
0x180049bbb  xor     r8d, r8d; bInitialState
0x180049bbe  xor     edx, edx; bManualReset
0x180049bc0  xor     ecx, ecx; lpEventAttributes
0x180049bc2  call    cs:__imp_CreateEventW
0x180049bc8  mov     rbx, rax
0x180049bcb  mov     [rsp+48h+arg_18], rax
0x180049bd0  inc     rax
0x180049bd3  test    rax, 0FFFFFFFFFFFFFFFEh
0x180049bd9  jnz     short loc_180049BF8
0x180049bdb  call    cs:__imp_GetLastError
0x180049be1  mov     edi, eax
0x180049be3  test    eax, eax
0x180049be5  jle     short loc_180049BF0
0x180049be7  movzx   edi, ax
0x180049bea  or      edi, 80070000h
0x180049bf0  test    edi, edi
0x180049bf2  jnz     loc_180049CF4
0x180049bf8  mov     [rsp+48h+arg_10], 0
0x180049c01  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049c08  jb      short loc_180049C3E
0x180049c0a  movsxd  rcx, dword ptr [r14]
0x180049c0d  mov     rax, [rbp+68h]
0x180049c11  mov     edx, 18h
0x180049c16  mov     [rsp+48h+var_20], rbp
0x180049c1b  mov     rax, [rax+rcx*8]
0x180049c1f  mov     [rsp+48h+var_28], rax
0x180049c24  mov     r9d, [r14]
0x180049c27  lea     r8, WPP_658c79110f173b2f2946ffe2569864d0_Traceguids
0x180049c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180049c35  mov     rcx, [rcx+10h]
0x180049c39  call    WPP_SF_dqq
0x180049c3e  movsxd  rcx, dword ptr [r14]
0x180049c41  mov     rax, [rbp+68h]
0x180049c45  mov     rsi, [rax+rcx*8]
0x180049c49  mov     rax, [rsi]
0x180049c4c  mov     rdi, [rax]
0x180049c4f  lea     rcx, [rsp+48h+arg_10]
0x180049c54  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180049c59  lea     r8, [rsp+48h+arg_10]
0x180049c5e  lea     rdx, _GUID_802302b0_82de_45e1_b421_f19ee5bdaf23
0x180049c65  mov     rcx, rsi
0x180049c68  mov     rax, rdi
0x180049c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c70  mov     edi, eax
0x180049c72  test    eax, eax
0x180049c74  jnz     short loc_180049CE9
0x180049c76  mov     rcx, [rsp+48h+arg_10]
0x180049c7b  mov     rax, [rcx]
0x180049c7e  mov     rdx, rbx
0x180049c81  mov     rax, [rax+18h]
0x180049c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c8a  mov     edi, eax
0x180049c8c  test    eax, eax
0x180049c8e  jnz     short loc_180049CE9
0x180049c90  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180049c93  mov     rcx, rbx; hHandle
0x180049c96  call    cs:__imp_WaitForSingleObject
0x180049c9c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049ca3  jb      short loc_180049CD7
0x180049ca5  movsxd  rcx, dword ptr [r14]
0x180049ca8  mov     rax, [rbp+68h]
0x180049cac  lea     edx, [rdi+19h]
0x180049caf  mov     [rsp+48h+var_20], rbp
0x180049cb4  mov     rax, [rax+rcx*8]
0x180049cb8  mov     [rsp+48h+var_28], rax
0x180049cbd  mov     r9d, [r14]
0x180049cc0  lea     r8, WPP_658c79110f173b2f2946ffe2569864d0_Traceguids
0x180049cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180049cce  mov     rcx, [rcx+10h]
0x180049cd2  call    WPP_SF_dqq
0x180049cd7  mov     rcx, [rsp+48h+arg_10]
0x180049cdc  mov     rax, [rcx]
0x180049cdf  mov     rax, [rax+20h]
0x180049ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ce8  nop
0x180049ce9  lea     rcx, [rsp+48h+arg_10]
0x180049cee  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180049cf3  nop
0x180049cf4  lea     rcx, [rsp+48h+arg_18]
0x180049cf9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180049cfe  mov     eax, edi
0x180049d00  mov     rbx, [rsp+48h+arg_0]
0x180049d05  mov     rbp, [rsp+48h+arg_8]
0x180049d0a  add     rsp, 30h
0x180049d0e  pop     r14
0x180049d10  pop     rdi
0x180049d11  pop     rsi
0x180049d12  retn
```
