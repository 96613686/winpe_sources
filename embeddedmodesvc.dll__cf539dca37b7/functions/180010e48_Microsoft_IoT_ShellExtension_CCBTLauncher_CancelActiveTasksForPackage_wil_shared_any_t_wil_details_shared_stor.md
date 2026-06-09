# Microsoft::IoT::ShellExtension::CCBTLauncher::CancelActiveTasksForPackage(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> const &,bool)

- ea: `0x180010e48`
- end: `0x180010ee1`
- name: `?CancelActiveTasksForPackage@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@_N@Z`
- size: `153`
- prototype: `__int64 __fastcall(Microsoft::IoT::ShellExtension::CCBTLauncher *this, char **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013284`

## callees

- `0x180008378`
- `0x180010e48`
- `0x180010f74`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::CancelActiveTasksForPackage(
        Microsoft::IoT::ShellExtension::CCBTLauncher *this,
        char **a2)
{
  struct Microsoft::IoT::ShellExtension::CCBT *i; // rbx
  char *v5; // rcx
  char *v6; // rax
  signed __int64 v7; // rcx
  int v8; // r8d
  int v9; // edx
  int v10; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  for ( i = (struct Microsoft::IoT::ShellExtension::CCBT *)*((_QWORD *)this + 20);
        i != *((struct Microsoft::IoT::ShellExtension::CCBT **)this + 21);
        i = (struct Microsoft::IoT::ShellExtension::CCBT *)((char *)i + 88) )
  {
    v5 = (char *)*((_QWORD *)i + 2);
    if ( v5 )
      v5 = *(char **)v5;
    v6 = *a2;
    if ( *a2 )
      v6 = *(char **)v6;
    v7 = v5 - v6;
    do
    {
      v8 = *(unsigned __int16 *)&v6[v7];
      v9 = *(unsigned __int16 *)v6 - v8;
      if ( v9 )
        break;
      v6 += 2;
    }
    while ( v8 );
    if ( !v9 )
    {
      v10 = Microsoft::IoT::ShellExtension::CCBTLauncher::CancelTask(this, i, v8);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1CF,
          (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
          (const char *)(unsigned int)v10);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180010e48  mov     [rsp+arg_0], rbx
0x180010e4d  mov     [rsp+arg_8], rsi
0x180010e52  push    rdi; int
0x180010e53  sub     rsp, 20h
0x180010e57  mov     rbx, [rcx+0A0h]
0x180010e5e  mov     rsi, rdx
0x180010e61  mov     rdi, rcx
0x180010e64  cmp     rbx, [rdi+0A8h]
0x180010e6b  jz      short loc_180010ECF
0x180010e6d  mov     rcx, [rbx+10h]
0x180010e71  test    rcx, rcx
0x180010e74  jz      short loc_180010E79
0x180010e76  mov     rcx, [rcx]
0x180010e79  mov     rax, [rsi]
0x180010e7c  test    rax, rax
0x180010e7f  jz      short loc_180010E84
0x180010e81  mov     rax, [rax]
0x180010e84  sub     rcx, rax
0x180010e87  movzx   edx, word ptr [rax]
0x180010e8a  movzx   r8d, word ptr [rax+rcx]; bool
0x180010e8f  sub     edx, r8d
0x180010e92  jnz     short loc_180010E9D
0x180010e94  add     rax, 2
0x180010e98  test    r8d, r8d
0x180010e9b  jnz     short loc_180010E87
0x180010e9d  test    edx, edx
0x180010e9f  jnz     short loc_180010EC9
0x180010ea1  mov     rdx, rbx; struct Microsoft::IoT::ShellExtension::CCBT *
0x180010ea4  mov     rcx, rdi; this
0x180010ea7  call    ?CancelTask@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJAEAVCCBT@234@_N@Z; Microsoft::IoT::ShellExtension::CCBTLauncher::CancelTask(Microsoft::IoT::ShellExtension::CCBT &,bool)
0x180010eac  test    eax, eax
0x180010eae  jns     short loc_180010EC9
0x180010eb0  mov     rcx, [rsp+28h]; this
0x180010eb5  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180010ebc  mov     r9d, eax; char *
0x180010ebf  mov     edx, 1CFh; void *
0x180010ec4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010ec9  add     rbx, 58h ; 'X'
0x180010ecd  jmp     short loc_180010E64
0x180010ecf  mov     rbx, [rsp+28h+arg_0]
0x180010ed4  xor     eax, eax
0x180010ed6  mov     rsi, [rsp+28h+arg_8]
0x180010edb  add     rsp, 20h
0x180010edf  pop     rdi
0x180010ee0  retn
```
