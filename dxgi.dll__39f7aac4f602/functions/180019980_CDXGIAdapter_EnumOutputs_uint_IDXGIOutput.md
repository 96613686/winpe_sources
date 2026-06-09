# CDXGIAdapter::EnumOutputs(uint,IDXGIOutput * *)

- ea: `0x180019980`
- end: `0x180019aca`
- name: `?EnumOutputs@CDXGIAdapter@@UEAAJIPEAPEAUIDXGIOutput@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(CDXGIAdapter *__hidden this, unsigned int, struct IDXGIOutput **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180019980`
- `0x180019ad0`
- `0x180075fa0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180019a13`
- `ntdll!EtwEventWrite` at `0x180019ab5`
- `ntdll!EtwEventWrite` at `0x180019a13`
- `ntdll!EtwEventWrite` at `0x180019ab5`

## pseudocode

```c
__int64 __fastcall CDXGIAdapter::EnumOutputs(CDXGIAdapter *this, unsigned int a2, struct IDXGIOutput **a3)
{
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+20h] [rbp-60h] BYREF
  char v9; // [rsp+28h] [rbp-58h]
  char v10; // [rsp+2Ch] [rbp-54h] BYREF
  __int16 v11; // [rsp+2Dh] [rbp-53h]
  char v12; // [rsp+2Fh] [rbp-51h]
  CDXGIAdapter *v13; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v14[2]; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v15[4]; // [rsp+48h] [rbp-38h] BYREF
  struct IDXGIOutput **v16; // [rsp+68h] [rbp-18h]
  __int64 v17; // [rsp+70h] [rbp-10h]

  v8 = a2;
  v13 = this;
  v9 = 0;
  if ( dword_180108134
    && (qword_180108120 & 0x4000000000000000LL) != 0
    && (qword_180108128 & 0x4000000000000000LL) == qword_180108128 )
  {
    v9 = 1;
    v15[0] = &v13;
    v15[2] = &v8;
    v15[1] = 8;
    v15[3] = 4;
    v17 = 8;
    if ( a3 )
      v16 = a3;
    else
      v16 = (struct IDXGIOutput **)v14;
    EtwEventWrite(DXGIEtwProviderGuid_Context, "v", 3, v15);
  }
  v6 = CDXGIAdapter::EnumOutputsImpl(this, a2, 1u, a3);
  v8 = v6;
  v11 = v6 >> 8;
  v12 = HIBYTE(v6);
  v10 = v6;
  if ( v9 )
  {
    v14[0] = &v10;
    v14[1] = 4;
    EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGIAdapter_EnumOutputs_Stop, 1, v14);
  }
  return v6;
}

```

## disassembly

```asm
0x180019980  mov     [rsp-18h+arg_18], rbx
0x180019985  push    rbp
0x180019986  push    rsi
0x180019987  push    rdi
0x180019988  mov     rbp, rsp
0x18001998b  sub     rsp, 80h
0x180019992  mov     rax, cs:__security_cookie
0x180019999  xor     rax, rsp
0x18001999c  mov     [rbp+var_8], rax
0x1800199a0  cmp     cs:dword_180108134, 0
0x1800199a7  mov     rbx, r8
0x1800199aa  mov     esi, edx
0x1800199ac  mov     [rbp+var_60], edx
0x1800199af  mov     rdi, rcx
0x1800199b2  mov     [rbp+var_50], rcx
0x1800199b6  mov     [rbp+var_58], 0
0x1800199ba  jnz     short loc_180019A3A
0x1800199bc  mov     r9, rbx; struct IDXGIOutput **
0x1800199bf  mov     r8d, 1; unsigned int
0x1800199c5  mov     edx, esi; unsigned int
0x1800199c7  mov     rcx, rdi; this
0x1800199ca  call    ?EnumOutputsImpl@CDXGIAdapter@@IEAAJIIPEAPEAUIDXGIOutput@@@Z; CDXGIAdapter::EnumOutputsImpl(uint,uint,IDXGIOutput * *)
0x1800199cf  cmp     [rbp+var_58], 0
0x1800199d3  mov     ebx, eax
0x1800199d5  mov     [rbp+var_60], eax
0x1800199d8  movzx   ecx, word ptr [rbp+var_60+1]
0x1800199dc  mov     [rbp+var_53], cx
0x1800199e0  mov     cl, byte ptr [rbp+var_60+3]
0x1800199e3  mov     [rbp+var_51], cl
0x1800199e6  mov     [rbp+var_54], bl
0x1800199e9  jz      short loc_180019A19
0x1800199eb  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x1800199f2  lea     rax, [rbp+var_54]
0x1800199f6  lea     r9, [rbp+var_48]
0x1800199fa  mov     [rbp+var_48], rax
0x1800199fe  mov     r8d, 1
0x180019a04  mov     [rbp+var_40], 4
0x180019a0c  lea     rdx, IDXGIAdapter_EnumOutputs_Stop
0x180019a13  call    cs:__imp_EtwEventWrite
0x180019a19  mov     eax, ebx
0x180019a1b  mov     rcx, [rbp+var_8]
0x180019a1f  xor     rcx, rsp; StackCookie
0x180019a22  call    __security_check_cookie
0x180019a27  mov     rbx, [rsp+80h+arg_18]
0x180019a2f  add     rsp, 80h
0x180019a36  pop     rdi
0x180019a37  pop     rsi
0x180019a38  pop     rbp
0x180019a39  retn
0x180019a3a  mov     rdx, 4000000000000000h
0x180019a44  test    cs:qword_180108120, rdx
0x180019a4b  jz      loc_1800199BC
0x180019a51  mov     rax, cs:qword_180108128
0x180019a58  and     rax, rdx
0x180019a5b  cmp     rax, cs:qword_180108128
0x180019a62  jnz     loc_1800199BC
0x180019a68  mov     [rbp+var_58], 1
0x180019a6c  lea     rax, [rbp+var_50]
0x180019a70  mov     [rbp+var_38], rax
0x180019a74  lea     rax, [rbp+var_60]
0x180019a78  mov     [rbp+var_28], rax
0x180019a7c  mov     [rbp+var_30], 8
0x180019a84  mov     [rbp+var_20], 4
0x180019a8c  mov     [rbp+var_10], 8
0x180019a94  test    rbx, rbx
0x180019a97  jz      short loc_180019AC0
0x180019a99  mov     [rbp+var_18], rbx
0x180019a9d  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x180019aa4  lea     r9, [rbp+var_38]
0x180019aa8  mov     r8d, 3
0x180019aae  lea     rdx, IDXGIAdapter_EnumOutputs_Start; "v"
0x180019ab5  call    cs:__imp_EtwEventWrite
0x180019abb  jmp     loc_1800199BC
0x180019ac0  lea     rax, [rbp+var_48]
0x180019ac4  mov     [rbp+var_18], rax
0x180019ac8  jmp     short loc_180019A9D
```
