# Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::StopUserSession(ulong)

- ea: `0x18000c1a4`
- end: `0x18000c264`
- name: `?StopUserSession@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@QEAAJK@Z`
- size: `192`
- prototype: `__int64 __fastcall(Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007cec`

## callees

- `0x180009fb0`
- `0x18000a238`
- `0x18000aefc`
- `0x18000c1a4`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::StopUserSession(
        Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *this,
        int a2)
{
  __int64 *v2; // rdi
  int *v5; // rax
  __int64 *v6; // rbx
  int v7; // eax
  __int64 *v8; // rsi
  __int64 *v9; // rsi
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF
  int v12; // [rsp+48h] [rbp+10h] BYREF

  v2 = (__int64 *)*((_QWORD *)this + 7);
  v12 = a2;
  v5 = (int *)std::_Pass_fn__lambda_9dc2194f0bf958aa2d9defda6b6fed4b___(&v11, &v12);
  v6 = (__int64 *)*((_QWORD *)this + 6);
  v7 = *v5;
  while ( v6 != v2 && *(_DWORD *)(*v6 + 184) != v7 )
    ++v6;
  if ( v6 != v2 )
  {
    v8 = v6 + 1;
    if ( v6 + 1 == v2 )
      goto LABEL_11;
    do
    {
      if ( *(_DWORD *)(*v8 + 184) != a2 )
        Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::operator=(v6++, v8);
      ++v8;
    }
    while ( v8 != v2 );
    if ( v6 != v2 )
    {
LABEL_11:
      v9 = (__int64 *)*((_QWORD *)this + 7);
      while ( v2 != v9 )
        Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::operator=(v6++, v2++);
      std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>(
        (__int64)v6,
        *((_QWORD *)this + 7));
      *((_QWORD *)this + 7) = v6;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c1a4  mov     rax, rsp
0x18000c1a7  mov     [rax+18h], rbx
0x18000c1ab  mov     [rax+20h], rbp
0x18000c1af  push    rsi
0x18000c1b0  push    rdi
0x18000c1b1  push    r14
0x18000c1b3  sub     rsp, 20h
0x18000c1b7  mov     rdi, [rcx+38h]
0x18000c1bb  mov     r14d, edx
0x18000c1be  mov     [rax+10h], edx
0x18000c1c1  mov     rbp, rcx
0x18000c1c4  lea     rdx, [rax+10h]
0x18000c1c8  lea     rcx, [rax+8]
0x18000c1cc  call    std___Pass_fn__lambda_9dc2194f0bf958aa2d9defda6b6fed4b___
0x18000c1d1  mov     rbx, [rbp+30h]
0x18000c1d5  mov     eax, [rax]
0x18000c1d7  jmp     short loc_18000C1E8
0x18000c1d9  mov     rcx, [rbx]
0x18000c1dc  cmp     [rcx+0B8h], eax
0x18000c1e2  jz      short loc_18000C1ED
0x18000c1e4  add     rbx, 8
0x18000c1e8  cmp     rbx, rdi
0x18000c1eb  jnz     short loc_18000C1D9
0x18000c1ed  cmp     rbx, rdi
0x18000c1f0  jz      short loc_18000C24F
0x18000c1f2  lea     rsi, [rbx+8]
0x18000c1f6  cmp     rsi, rdi
0x18000c1f9  jz      short loc_18000C224
0x18000c1fb  mov     rax, [rsi]
0x18000c1fe  cmp     [rax+0B8h], r14d
0x18000c205  jz      short loc_18000C216
0x18000c207  mov     rdx, rsi
0x18000c20a  mov     rcx, rbx
0x18000c20d  call    ??4?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::operator=(Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> &&)
0x18000c212  add     rbx, 8
0x18000c216  add     rsi, 8
0x18000c21a  cmp     rsi, rdi
0x18000c21d  jnz     short loc_18000C1FB
0x18000c21f  cmp     rbx, rdi
0x18000c222  jz      short loc_18000C24F
0x18000c224  mov     rsi, [rbp+38h]
0x18000c228  jmp     short loc_18000C23A
0x18000c22a  mov     rdx, rdi
0x18000c22d  call    ??4?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::operator=(Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> &&)
0x18000c232  add     rbx, 8
0x18000c236  add     rdi, 8
0x18000c23a  mov     rcx, rbx
0x18000c23d  cmp     rdi, rsi
0x18000c240  jnz     short loc_18000C22A
0x18000c242  mov     rdx, [rbp+38h]
0x18000c246  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>(Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> *,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> * const,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>> &)
0x18000c24b  mov     [rbp+38h], rbx
0x18000c24f  mov     rbx, [rsp+38h+arg_10]
0x18000c254  xor     eax, eax
0x18000c256  mov     rbp, [rsp+38h+arg_18]
0x18000c25b  add     rsp, 20h
0x18000c25f  pop     r14
0x18000c261  pop     rdi
0x18000c262  pop     rsi
0x18000c263  retn
```
