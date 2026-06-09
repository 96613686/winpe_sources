# SleepOrIdle(ID3D11Device *,int)

- ea: `0x180056130`
- end: `0x1800562bf`
- name: `?SleepOrIdle@@YAXPEAUID3D11Device@@H@Z`
- size: `399`
- prototype: `void __fastcall(struct ID3D11Device *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004fed0`

## callees

- `0x18004a11c`
- `0x180056130`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005614b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005614b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005629b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005629b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800562a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800562a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SleepOrIdle(struct ID3D11Device *a1)
{
  HANDLE EventW; // rsi
  HRESULT (__stdcall *QueryInterface)(ID3D11Device *, const IID *const, void **); // rbx
  __int64 v4; // rdi
  unsigned int (__fastcall *v5)(__int64, _QWORD, _QWORD, GUID *, __int64 *); // rbx
  void (__stdcall *GetImmediateContext)(ID3D11Device *, ID3D11DeviceContext **); // rbx
  unsigned int (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rdi
  unsigned int (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rbx
  unsigned int (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-10h] BYREF
  __int64 v10; // [rsp+38h] [rbp-8h] BYREF
  __int64 v11; // [rsp+80h] [rbp+40h] BYREF
  __int64 v12; // [rsp+88h] [rbp+48h] BYREF

  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v11 = 0;
    v10 = 0;
    QueryInterface = a1->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v10);
    if ( !((unsigned int (__fastcall *)(struct ID3D11Device *, GUID *, __int64 *))QueryInterface)(
            a1,
            &GUID_8ffde202_a0e7_45df_9e01_e837801b5ea0,
            &v10) )
    {
      v4 = v10;
      v5 = *(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, GUID *, __int64 *))(*(_QWORD *)v10 + 544LL);
      Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v11);
      if ( !v5(v4, 0, 0, &GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80, &v11)
        && !(*(unsigned int (__fastcall **)(__int64, __int64, HANDLE))(*(_QWORD *)v11 + 72LL))(v11, 1, EventW) )
      {
        v9 = 0;
        GetImmediateContext = a1->lpVtbl->GetImmediateContext;
        Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v9);
        ((void (__fastcall *)(struct ID3D11Device *, unsigned int (__fastcall ****)(_QWORD, GUID *, __int64 *)))GetImmediateContext)(
          a1,
          &v9);
        v12 = 0;
        v7 = (unsigned int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v9;
        v8 = **v9;
        Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v12);
        if ( !v8(v7, &GUID_917600da_f58c_4c33_98d8_3e15b390fa24, &v12) )
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 1176LL))(v12, v11, 1);
        Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v12);
        Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v9);
      }
    }
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v10);
    WaitForSingleObject(EventW, 4u);
    CloseHandle(EventW);
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v11);
  }
}

```

## disassembly

```asm
0x180056130  push    rbp
0x180056132  push    rbx
0x180056133  push    rsi
0x180056134  push    rdi
0x180056135  push    r14
0x180056137  mov     rbp, rsp
0x18005613a  sub     rsp, 40h
0x18005613e  mov     r14, rcx
0x180056141  xor     r9d, r9d; lpName
0x180056144  xor     r8d, r8d; bInitialState
0x180056147  xor     edx, edx; bManualReset
0x180056149  xor     ecx, ecx; lpEventAttributes
0x18005614b  call    cs:__imp_CreateEventW
0x180056151  mov     rsi, rax
0x180056154  test    rax, rax
0x180056157  jz      loc_1800562B4
0x18005615d  mov     [rbp+arg_10], 0
0x180056165  mov     [rbp+var_8], 0
0x18005616d  mov     rcx, [r14]
0x180056170  mov     rbx, [rcx]
0x180056173  lea     rcx, [rbp+var_8]
0x180056177  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18005617c  lea     r8, [rbp+var_8]
0x180056180  lea     rdx, _GUID_8ffde202_a0e7_45df_9e01_e837801b5ea0
0x180056187  mov     rcx, r14
0x18005618a  mov     rax, rbx
0x18005618d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056192  test    eax, eax
0x180056194  jnz     loc_18005628A
0x18005619a  mov     rdi, [rbp+var_8]
0x18005619e  mov     rax, [rdi]
0x1800561a1  mov     rbx, [rax+220h]
0x1800561a8  lea     rcx, [rbp+arg_10]
0x1800561ac  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x1800561b1  lea     rax, [rbp+arg_10]
0x1800561b5  mov     [rsp+40h+var_20], rax
0x1800561ba  lea     r9, _GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80
0x1800561c1  xor     r8d, r8d
0x1800561c4  xor     edx, edx
0x1800561c6  mov     rcx, rdi
0x1800561c9  mov     rax, rbx
0x1800561cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561d1  test    eax, eax
0x1800561d3  jnz     loc_18005628A
0x1800561d9  mov     rcx, [rbp+arg_10]
0x1800561dd  mov     rax, [rcx]
0x1800561e0  mov     r8, rsi
0x1800561e3  mov     edx, 1
0x1800561e8  mov     rax, [rax+48h]
0x1800561ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561f1  test    eax, eax
0x1800561f3  jnz     loc_18005628A
0x1800561f9  mov     [rbp+var_10], 0
0x180056201  mov     rax, [r14]
0x180056204  mov     rbx, [rax+140h]
0x18005620b  lea     rcx, [rbp+var_10]
0x18005620f  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180056214  lea     rdx, [rbp+var_10]
0x180056218  mov     rcx, r14
0x18005621b  mov     rax, rbx
0x18005621e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056223  mov     [rbp+arg_18], 0
0x18005622b  mov     rdi, [rbp+var_10]
0x18005622f  mov     rax, [rdi]
0x180056232  mov     rbx, [rax]
0x180056235  lea     rcx, [rbp+arg_18]
0x180056239  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18005623e  lea     r8, [rbp+arg_18]
0x180056242  lea     rdx, _GUID_917600da_f58c_4c33_98d8_3e15b390fa24
0x180056249  mov     rcx, rdi
0x18005624c  mov     rax, rbx
0x18005624f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056254  test    eax, eax
0x180056256  jnz     short loc_180056276
0x180056258  mov     rcx, [rbp+arg_18]
0x18005625c  mov     rax, [rcx]
0x18005625f  mov     r8d, 1
0x180056265  mov     rdx, [rbp+arg_10]
0x180056269  mov     rax, [rax+498h]
0x180056270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056275  nop
0x180056276  lea     rcx, [rbp+arg_18]
0x18005627a  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18005627f  nop
0x180056280  lea     rcx, [rbp+var_10]
0x180056284  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180056289  nop
0x18005628a  lea     rcx, [rbp+var_8]
0x18005628e  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180056293  mov     edx, 4; dwMilliseconds
0x180056298  mov     rcx, rsi; hHandle
0x18005629b  call    cs:__imp_WaitForSingleObject
0x1800562a1  mov     rcx, rsi; hObject
0x1800562a4  call    cs:__imp_CloseHandle
0x1800562aa  nop
0x1800562ab  lea     rcx, [rbp+arg_10]
0x1800562af  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x1800562b4  add     rsp, 40h
0x1800562b8  pop     r14
0x1800562ba  pop     rdi
0x1800562bb  pop     rsi
0x1800562bc  pop     rbx
0x1800562bd  pop     rbp
0x1800562be  retn
```
