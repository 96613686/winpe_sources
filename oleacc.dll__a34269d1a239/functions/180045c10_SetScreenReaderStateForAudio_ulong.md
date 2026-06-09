# SetScreenReaderStateForAudio(ulong)

- ea: `0x180045c10`
- end: `0x180045d42`
- name: `?SetScreenReaderStateForAudio@@YAJK@Z`
- size: `306`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045f04`

## callees

- `0x18001e010`
- `0x180045be4`
- `0x180045c10`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045c52`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045c52`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetScreenReaderStateForAudio(char a1)
{
  HRESULT v2; // ebx
  LPVOID v3; // rcx
  __int64 v4; // rdx
  LPVOID ppv; // [rsp+48h] [rbp+18h] BYREF

  ppv = 0;
  Microsoft::WRL::ComPtr<IPolicyConfig>::InternalRelease(&ppv);
  v2 = CoCreateInstance(
         &GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9,
         0,
         0x17u,
         &GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46,
         &ppv);
  if ( v2 < 0 )
    goto LABEL_16;
  v3 = ppv;
  if ( !ppv )
    goto LABEL_16;
  if ( (a1 & 4) != 0 )
  {
    if ( (a1 & 0x10) == 0 )
    {
      v2 = SetScreenReaderStaticDuckingValue(0xFFFFFFEE);
      if ( v2 >= 0 )
      {
        v2 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 120LL))(ppv, 1);
        if ( v2 >= 0 )
          goto LABEL_15;
      }
      goto LABEL_16;
    }
    v2 = SetScreenReaderStaticDuckingValue(0);
    if ( v2 < 0 )
      goto LABEL_16;
    v3 = ppv;
    v4 = 1;
  }
  else
  {
    if ( (a1 & 8) != 0 )
    {
      if ( (int)SetScreenReaderStaticDuckingValue(0) >= 0 )
        (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 120LL))(ppv, 1);
      goto LABEL_15;
    }
    v4 = 0;
  }
  v2 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v3 + 120LL))(v3, v4);
  if ( v2 >= 0 )
LABEL_15:
    v2 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)ppv + 144LL))(ppv, L"SR");
LABEL_16:
  Microsoft::WRL::ComPtr<IPolicyConfig>::InternalRelease(&ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180045c10  mov     [rsp-8+arg_0], rbx
0x180045c15  mov     [rsp-8+arg_10], rdi
0x180045c1a  push    rbp
0x180045c1b  mov     rbp, rsp
0x180045c1e  sub     rsp, 30h
0x180045c22  mov     edi, ecx
0x180045c24  mov     [rbp+arg_8], 0
0x180045c2c  lea     rcx, [rbp+arg_8]
0x180045c30  call    ?InternalRelease@?$ComPtr@UIPolicyConfig@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPolicyConfig>::InternalRelease(void)
0x180045c35  lea     rax, [rbp+arg_8]
0x180045c39  mov     [rsp+30h+ppv], rax; ppv
0x180045c3e  lea     r9, _GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46; riid
0x180045c45  xor     edx, edx; pUnkOuter
0x180045c47  lea     r8d, [rdx+17h]; dwClsContext
0x180045c4b  lea     rcx, _GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9; rclsid
0x180045c52  call    cs:__imp_CoCreateInstance
0x180045c58  mov     ebx, eax
0x180045c5a  test    eax, eax
0x180045c5c  js      loc_180045D27
0x180045c62  mov     rcx, [rbp+arg_8]
0x180045c66  test    rcx, rcx
0x180045c69  jz      loc_180045D27
0x180045c6f  test    dil, 4
0x180045c73  jnz     short loc_180045CBF
0x180045c75  test    dil, 8
0x180045c79  jnz     short loc_180045C9D
0x180045c7b  xor     edx, edx
0x180045c7d  mov     rax, [rcx]
0x180045c80  mov     rax, [rax+78h]
0x180045c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c89  mov     ebx, eax
0x180045c8b  test    eax, eax
0x180045c8d  js      loc_180045D27
0x180045c93  movss   xmm2, cs:__real@c1900000
0x180045c9b  jmp     short loc_180045D0B
0x180045c9d  xor     ecx, ecx; unsigned int
0x180045c9f  call    ?SetScreenReaderStaticDuckingValue@@YAJH@Z; SetScreenReaderStaticDuckingValue(int)
0x180045ca4  test    eax, eax
0x180045ca6  js      short loc_180045D08
0x180045ca8  mov     rcx, [rbp+arg_8]
0x180045cac  mov     rax, [rcx]
0x180045caf  mov     edx, 1
0x180045cb4  mov     rax, [rax+78h]
0x180045cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cbd  jmp     short loc_180045D08
0x180045cbf  test    dil, 10h
0x180045cc3  jz      short loc_180045CDD
0x180045cc5  xor     ecx, ecx; unsigned int
0x180045cc7  call    ?SetScreenReaderStaticDuckingValue@@YAJH@Z; SetScreenReaderStaticDuckingValue(int)
0x180045ccc  mov     ebx, eax
0x180045cce  test    eax, eax
0x180045cd0  js      short loc_180045D27
0x180045cd2  mov     rcx, [rbp+arg_8]
0x180045cd6  mov     edx, 1
0x180045cdb  jmp     short loc_180045C7D
0x180045cdd  mov     ecx, 0FFFFFFEEh; unsigned int
0x180045ce2  call    ?SetScreenReaderStaticDuckingValue@@YAJH@Z; SetScreenReaderStaticDuckingValue(int)
0x180045ce7  mov     ebx, eax
0x180045ce9  test    eax, eax
0x180045ceb  js      short loc_180045D27
0x180045ced  mov     rcx, [rbp+arg_8]
0x180045cf1  mov     rax, [rcx]
0x180045cf4  mov     edx, 1
0x180045cf9  mov     rax, [rax+78h]
0x180045cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d02  mov     ebx, eax
0x180045d04  test    eax, eax
0x180045d06  js      short loc_180045D27
0x180045d08  xorps   xmm2, xmm2
0x180045d0b  mov     rcx, [rbp+arg_8]
0x180045d0f  mov     rax, [rcx]
0x180045d12  lea     rdx, aSr; "SR"
0x180045d19  mov     rax, [rax+90h]
0x180045d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d25  mov     ebx, eax
0x180045d27  lea     rcx, [rbp+arg_8]
0x180045d2b  call    ?InternalRelease@?$ComPtr@UIPolicyConfig@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPolicyConfig>::InternalRelease(void)
0x180045d30  mov     eax, ebx
0x180045d32  mov     rbx, [rsp+30h+arg_0]
0x180045d37  mov     rdi, [rsp+30h+arg_10]
0x180045d3c  add     rsp, 30h
0x180045d40  pop     rbp
0x180045d41  retn
```
