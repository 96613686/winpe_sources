# CDXGISwapChain::GetFullscreenState(int *,IDXGIOutput * *)

- ea: `0x180036950`
- end: `0x180036b4b`
- name: `?GetFullscreenState@CDXGISwapChain@@UEAAJPEAHPEAPEAUIDXGIOutput@@@Z`
- size: `507`
- prototype: `__int64 __fastcall(CDXGISwapChain *__hidden this, int *, struct IDXGIOutput **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180035408`

## callees

- `0x1800202ac`
- `0x180036950`
- `0x180075fa0`
- `0x1800cb010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180036a3d`
- `ntdll!EtwEventWrite` at `0x180036ad5`
- `ntdll!EtwEventWrite` at `0x180036a3d`
- `ntdll!EtwEventWrite` at `0x180036ad5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDXGISwapChain::GetFullscreenState(CDXGISwapChain *this, int *a2, struct IDXGIOutput **a3)
{
  char *v6; // rdi
  int v7; // eax
  void (__fastcall ***v9)(_QWORD, GUID *, struct IDXGIOutput **); // rcx
  char v10; // [rsp+20h] [rbp-60h]
  int v11; // [rsp+24h] [rbp-5Ch] BYREF
  _QWORD v12[2]; // [rsp+28h] [rbp-58h] BYREF
  _QWORD v13[2]; // [rsp+38h] [rbp-48h] BYREF
  int *v14; // [rsp+48h] [rbp-38h]
  __int64 v15; // [rsp+50h] [rbp-30h]
  struct IDXGIOutput **v16; // [rsp+58h] [rbp-28h]
  __int64 v17; // [rsp+60h] [rbp-20h]
  char v18; // [rsp+68h] [rbp-18h] BYREF

  v12[0] = this;
  v10 = 0;
  if ( dword_180108134
    && (qword_180108120 & 0x4000000000000000LL) != 0
    && (qword_180108128 & 0x4000000000000000LL) == qword_180108128 )
  {
    v10 = 1;
    v13[0] = v12;
    v13[1] = 8;
    v15 = 4;
    if ( a2 )
      v14 = a2;
    else
      v14 = (int *)&v18;
    v17 = 8;
    if ( a3 )
      v16 = a3;
    else
      v16 = (struct IDXGIOutput **)&v18;
    EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGISwapChain_GetFullscreenState_Start, 3, v13);
  }
  v6 = (char *)this + 136;
  if ( !this )
    v6 = 0;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 1) + 24LL))(*((_QWORD *)v6 + 1));
  if ( *((_DWORD *)this + 551) )
    CDXGISwapChain::ScenarioEnterOrLeaveFullscreen(this, 0, 0);
  if ( a2 )
  {
    v7 = 0;
    if ( !*((_DWORD *)this + 551) )
      LOBYTE(v7) = *((_DWORD *)this + 111) == 0;
    *a2 = v7;
  }
  if ( a3 )
  {
    v9 = (void (__fastcall ***)(_QWORD, GUID *, struct IDXGIOutput **))*((_QWORD *)this + 266);
    if ( !v9 || *((_DWORD *)this + 111) )
      *a3 = 0;
    else
      (**v9)(v9, &GUID_ae02eedb_c735_4690_8d52_5a8dc20213aa, a3);
  }
  v11 = 0;
  if ( v6 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 1) + 32LL))(*((_QWORD *)v6 + 1));
  if ( v10 )
  {
    v12[0] = &v11;
    v12[1] = 4;
    EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGISwapChain_GetFullscreenState_Stop, 1, v12);
  }
  return 0;
}

```

## disassembly

```asm
0x180036950  mov     [rsp-28h+arg_18], rbx
0x180036955  push    rbp
0x180036956  push    rsi
0x180036957  push    rdi
0x180036958  push    r14
0x18003695a  push    r15
0x18003695c  mov     rbp, rsp
0x18003695f  sub     rsp, 80h
0x180036966  mov     rax, cs:__security_cookie
0x18003696d  xor     rax, rsp
0x180036970  mov     [rbp+var_10], rax
0x180036974  mov     r14, r8
0x180036977  mov     rsi, rdx
0x18003697a  mov     rbx, rcx
0x18003697d  mov     [rbp+var_58], rcx
0x180036981  mov     [rbp+var_60], 0
0x180036985  xor     r15d, r15d
0x180036988  cmp     cs:dword_180108134, r15d
0x18003698f  jz      short loc_1800369A8
0x180036991  mov     rdx, 4000000000000000h
0x18003699b  test    cs:qword_180108120, rdx
0x1800369a2  jnz     loc_180036A68
0x1800369a8  lea     rdi, [rbx+88h]
0x1800369af  test    rbx, rbx
0x1800369b2  cmovz   rdi, r15
0x1800369b6  mov     rcx, [rdi+8]
0x1800369ba  mov     rax, [rcx]
0x1800369bd  mov     rax, [rax+18h]
0x1800369c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369c6  mov     eax, [rbx+89Ch]
0x1800369cc  test    eax, eax
0x1800369ce  jnz     loc_180036B39
0x1800369d4  test    rsi, rsi
0x1800369d7  jz      short loc_1800369EC
0x1800369d9  mov     eax, [rbx+89Ch]
0x1800369df  test    eax, eax
0x1800369e1  mov     eax, r15d
0x1800369e4  jz      loc_180036AE0
0x1800369ea  mov     [rsi], eax
0x1800369ec  test    r14, r14
0x1800369ef  jnz     loc_180036AEF
0x1800369f5  mov     [rbp+var_5C], r15d
0x1800369f9  test    rdi, rdi
0x1800369fc  jz      short loc_180036A0F
0x1800369fe  mov     rcx, [rdi+8]
0x180036a02  mov     rax, [rcx]
0x180036a05  mov     rax, [rax+20h]
0x180036a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a0e  nop
0x180036a0f  cmp     [rbp+var_60], 0
0x180036a13  jz      short loc_180036A43
0x180036a15  lea     rax, [rbp+var_5C]
0x180036a19  mov     [rbp+var_58], rax
0x180036a1d  mov     [rbp+var_50], 4
0x180036a25  lea     r9, [rbp+var_58]
0x180036a29  mov     r8d, 1
0x180036a2f  lea     rdx, IDXGISwapChain_GetFullscreenState_Stop
0x180036a36  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x180036a3d  call    cs:__imp_EtwEventWrite
0x180036a43  xor     eax, eax
0x180036a45  mov     rcx, [rbp+var_10]
0x180036a49  xor     rcx, rsp; StackCookie
0x180036a4c  call    __security_check_cookie
0x180036a51  mov     rbx, [rsp+80h+arg_18]
0x180036a59  add     rsp, 80h
0x180036a60  pop     r15
0x180036a62  pop     r14
0x180036a64  pop     rdi
0x180036a65  pop     rsi
0x180036a66  pop     rbp
0x180036a67  retn
0x180036a68  mov     rax, cs:qword_180108128
0x180036a6f  and     rax, rdx
0x180036a72  cmp     rax, cs:qword_180108128
0x180036a79  jnz     loc_1800369A8
0x180036a7f  mov     [rbp+var_60], 1
0x180036a83  lea     rax, [rbp+var_58]
0x180036a87  mov     [rbp+var_48], rax
0x180036a8b  mov     [rbp+var_40], 8
0x180036a93  mov     [rbp+var_30], 4
0x180036a9b  test    rsi, rsi
0x180036a9e  jz      loc_180036B2C
0x180036aa4  mov     [rbp+var_38], rsi
0x180036aa8  mov     [rbp+var_20], 8
0x180036ab0  test    r14, r14
0x180036ab3  jnz     short loc_180036B26
0x180036ab5  lea     rax, [rbp+var_18]
0x180036ab9  mov     [rbp+var_28], rax
0x180036abd  lea     r9, [rbp+var_48]
0x180036ac1  mov     r8d, 3
0x180036ac7  lea     rdx, IDXGISwapChain_GetFullscreenState_Start
0x180036ace  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x180036ad5  call    cs:__imp_EtwEventWrite
0x180036adb  jmp     loc_1800369A8
0x180036ae0  cmp     [rbx+1BCh], r15d
0x180036ae7  setz    al
0x180036aea  jmp     loc_1800369EA
0x180036aef  mov     rcx, [rbx+850h]
0x180036af6  test    rcx, rcx
0x180036af9  jz      short loc_180036B1E
0x180036afb  cmp     [rbx+1BCh], r15d
0x180036b02  jnz     short loc_180036B1E
0x180036b04  mov     rax, [rcx]
0x180036b07  mov     r8, r14
0x180036b0a  lea     rdx, _GUID_ae02eedb_c735_4690_8d52_5a8dc20213aa
0x180036b11  mov     rax, [rax]
0x180036b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b19  jmp     loc_1800369F5
0x180036b1e  mov     [r14], r15
0x180036b21  jmp     loc_1800369F5
0x180036b26  mov     [rbp+var_28], r14
0x180036b2a  jmp     short loc_180036ABD
0x180036b2c  lea     rax, [rbp+var_18]
0x180036b30  mov     [rbp+var_38], rax
0x180036b34  jmp     loc_180036AA8
0x180036b39  xor     r8d, r8d; bool
0x180036b3c  xor     edx, edx; struct CDXGIOutput *
0x180036b3e  mov     rcx, rbx; this
0x180036b41  call    ?ScenarioEnterOrLeaveFullscreen@CDXGISwapChain@@QEAAJPEAVCDXGIOutput@@_N@Z; CDXGISwapChain::ScenarioEnterOrLeaveFullscreen(CDXGIOutput *,bool)
0x180036b46  jmp     loc_1800369D4
```
