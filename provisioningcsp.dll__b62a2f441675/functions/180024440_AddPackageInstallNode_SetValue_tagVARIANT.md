# AddPackageInstallNode::SetValue(tagVARIANT)

- ea: `0x180024440`
- end: `0x1800244ff`
- name: `?SetValue@AddPackageInstallNode@@UEAAJUtagVARIANT@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(PVOID pv, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180006954`
- `0x180006974`
- `0x180024440`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180024491`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180024491`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800244dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800244dc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800244cd`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800244cd`

## string_xrefs

- `0x18002445d`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`
- `0x1800244aa`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`

## pseudocode

```c
__int64 __fastcall AddPackageInstallNode::SetValue(PVOID pv, struct tagVARIANT *a2)
{
  SHORT iVal; // di
  struct _TP_WORK *ThreadpoolWork; // rsi
  const char *v6; // r9
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2->vt != 11 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
      (const char *)0x80070057LL,
      v7);
    return 2147942487LL;
  }
  iVal = a2->iVal;
  if ( iVal == -1 )
  {
    ThreadpoolWork = CreateThreadpoolWork(AddPackageInstallNode::LaunchAddPackageThreadProc, pv, 0);
    if ( !ThreadpoolWork )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x41,
               (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
               v6);
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)pv + 8LL))(pv);
    SubmitThreadpoolWork(ThreadpoolWork);
    CloseThreadpoolWork(ThreadpoolWork);
  }
  *((_WORD *)pv + 12) = iVal;
  return 0;
}

```

## disassembly

```asm
0x180024440  mov     [rsp+arg_0], rbx
0x180024445  mov     [rsp+arg_8], rsi
0x18002444a  push    rdi; int
0x18002444b  sub     rsp, 20h
0x18002444f  cmp     word ptr [rdx], 0Bh
0x180024453  mov     rbx, rcx
0x180024456  jz      short loc_18002447A
0x180024458  mov     rcx, [rsp+28h]; this
0x18002445d  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\provcsp\\addpa"...
0x180024464  mov     ebx, 80070057h
0x180024469  mov     edx, 3Ch ; '<'; void *
0x18002446e  mov     r9d, ebx; char *
0x180024471  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024476  mov     eax, ebx
0x180024478  jmp     short loc_1800244EE
0x18002447a  movzx   edi, word ptr [rdx+8]
0x18002447e  cmp     di, 0FFFFh
0x180024482  jnz     short loc_1800244E8
0x180024484  xor     r8d, r8d; pcbe
0x180024487  lea     rcx, ?LaunchAddPackageThreadProc@AddPackageInstallNode@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002448e  mov     rdx, rbx; pv
0x180024491  call    cs:__imp_CreateThreadpoolWork
0x180024498  nop     dword ptr [rax+rax+00h]
0x18002449d  mov     rsi, rax
0x1800244a0  test    rax, rax
0x1800244a3  jnz     short loc_1800244BB
0x1800244a5  mov     rcx, [rsp+28h]; this
0x1800244aa  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\provcsp\\addpa"...
0x1800244b1  lea     edx, [rax+41h]; void *
0x1800244b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800244b9  jmp     short loc_1800244EE
0x1800244bb  mov     rax, [rbx]
0x1800244be  mov     rcx, rbx
0x1800244c1  mov     rax, [rax+8]
0x1800244c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244ca  mov     rcx, rsi; pwk
0x1800244cd  call    cs:__imp_SubmitThreadpoolWork
0x1800244d4  nop     dword ptr [rax+rax+00h]
0x1800244d9  mov     rcx, rsi; pwk
0x1800244dc  call    cs:__imp_CloseThreadpoolWork
0x1800244e3  nop     dword ptr [rax+rax+00h]
0x1800244e8  mov     [rbx+18h], di
0x1800244ec  xor     eax, eax
0x1800244ee  mov     rbx, [rsp+28h+arg_0]
0x1800244f3  mov     rsi, [rsp+28h+arg_8]
0x1800244f8  add     rsp, 20h
0x1800244fc  pop     rdi
0x1800244fd  retn
```
