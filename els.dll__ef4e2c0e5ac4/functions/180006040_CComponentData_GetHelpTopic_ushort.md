# CComponentData::GetHelpTopic(ushort * *)

- ea: `0x180006040`
- end: `0x18000614c`
- name: `?GetHelpTopic@CComponentData@@UEAAJPEAPEAG@Z`
- size: `268`
- prototype: `__int64 __fastcall(CComponentData *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001750`
- `0x180001910`
- `0x18000265c`
- `0x1800050ac`
- `0x180006040`
- `0x1800222d0`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180006082`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180006082`
- `ole32!CoTaskMemAlloc` at `0x1800060d1`
- `ole32!CoTaskMemAlloc` at `0x1800060d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CComponentData::GetHelpTopic(CComponentData *this, unsigned __int16 **a2)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  __int64 v8; // rdx
  _QWORD *v9; // rdx
  __int64 v10; // rdx
  _QWORD v11[2]; // [rsp+20h] [rbp-268h] BYREF
  __int64 v12; // [rsp+30h] [rbp-258h]
  unsigned __int64 v13; // [rsp+38h] [rbp-250h]
  _BYTE v14[32]; // [rsp+40h] [rbp-248h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-228h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
    return 2147549183LL;
  v4 = std::wstring::wstring(v14, Buffer);
  std::operator+<unsigned short>(v11, v4, L"\\help\\els.chm");
  LOBYTE(v5) = 1;
  std::wstring::_Tidy(v14, v5, 0);
  v6 = v12;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v12 + 2);
  *a2 = v7;
  if ( !v7 )
  {
    LOBYTE(v8) = 1;
    std::wstring::_Tidy(v11, v8, 0);
    return 2147549183LL;
  }
  v9 = v11;
  if ( v13 >= 8 )
    v9 = (_QWORD *)v11[0];
  std::char_traits<unsigned short>::copy(v7, v9, v6);
  (*a2)[v6] = 0;
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v11, v10, 0);
  return 0;
}

```

## disassembly

```asm
0x180006040  mov     [rsp+arg_0], rbx
0x180006045  push    rdi
0x180006046  sub     rsp, 280h
0x18000604d  mov     rax, cs:__security_cookie
0x180006054  xor     rax, rsp
0x180006057  mov     [rsp+288h+var_18], rax
0x18000605f  mov     rbx, rdx
0x180006062  test    rdx, rdx
0x180006065  jnz     short loc_180006071
0x180006067  mov     eax, 80004003h
0x18000606c  jmp     loc_18000612B
0x180006071  mov     qword ptr [rdx], 0
0x180006078  mov     edx, 104h; uSize
0x18000607d  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x180006082  call    cs:__imp_GetSystemWindowsDirectoryW
0x180006088  test    eax, eax
0x18000608a  jz      loc_180006126
0x180006090  lea     rdx, [rsp+288h+Buffer]
0x180006095  lea     rcx, [rsp+288h+var_248]
0x18000609a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000609f  nop
0x1800060a0  lea     r8, aHelpElsChm; "\\help\\els.chm"
0x1800060a7  mov     rdx, rax
0x1800060aa  lea     rcx, [rsp+288h+var_268]
0x1800060af  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x1800060b4  nop
0x1800060b5  xor     r8d, r8d
0x1800060b8  mov     dl, 1
0x1800060ba  lea     rcx, [rsp+288h+var_248]
0x1800060bf  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800060c4  mov     rdi, [rsp+288h+var_258]
0x1800060c9  lea     rcx, ds:2[rdi*2]; cb
0x1800060d1  call    cs:__imp_CoTaskMemAlloc
0x1800060d7  mov     [rbx], rax
0x1800060da  test    rax, rax
0x1800060dd  jz      short loc_180006117
0x1800060df  lea     rdx, [rsp+288h+var_268]
0x1800060e4  cmp     [rsp+288h+var_250], 8
0x1800060ea  cmovnb  rdx, [rsp+288h+var_268]
0x1800060f0  mov     r8, rdi
0x1800060f3  mov     rcx, rax
0x1800060f6  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x1800060fb  mov     rcx, [rbx]
0x1800060fe  xor     eax, eax
0x180006100  mov     [rcx+rdi*2], ax
0x180006104  xor     r8d, r8d
0x180006107  mov     dl, 1
0x180006109  lea     rcx, [rsp+288h+var_268]
0x18000610e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180006113  xor     eax, eax
0x180006115  jmp     short loc_18000612B
0x180006117  xor     r8d, r8d
0x18000611a  mov     dl, 1
0x18000611c  lea     rcx, [rsp+288h+var_268]
0x180006121  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180006126  mov     eax, 8000FFFFh
0x18000612b  mov     rcx, [rsp+288h+var_18]
0x180006133  xor     rcx, rsp; StackCookie
0x180006136  call    __security_check_cookie
0x18000613b  mov     rbx, [rsp+288h+arg_0]
0x180006143  add     rsp, 280h
0x18000614a  pop     rdi
0x18000614b  retn
```
