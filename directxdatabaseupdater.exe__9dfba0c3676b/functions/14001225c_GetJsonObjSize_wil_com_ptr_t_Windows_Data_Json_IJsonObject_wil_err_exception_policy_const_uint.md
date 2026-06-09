# GetJsonObjSize(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &,uint *)

- ea: `0x14001225c`
- end: `0x1400122ef`
- name: `?GetJsonObjSize@@YAJAEBV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@PEAI@Z`
- size: `147`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400122f8`

## callees

- `0x140005cac`
- `0x14000a4bc`
- `0x14001225c`
- `0x14001a010`

## string_xrefs

- `0x1400122c0`: `onecore\windows\directx\database\updater\exe\onesettingshelper.cpp`

## pseudocode

```c
__int64 __fastcall GetJsonObjSize(__int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *), __int64 a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v4)(_QWORD, GUID *, __int64 *); // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF

  v11 = 0;
  v3 = *a1;
  v4 = *v3;
  v11 = 0;
  v5 = (*v4)(v3, &GUID_c9d9a725_786b_5113_b4b7_9b61764c220b, &v11);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 56LL))(v11, a2);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v6 = 0;
      goto LABEL_7;
    }
    v7 = 31;
  }
  else
  {
    v7 = 29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\onesettingshelper.cpp",
    (const char *)(unsigned int)v5,
    v9);
LABEL_7:
  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v11);
  return v6;
}

```

## disassembly

```asm
0x14001225c  mov     r11, rsp
0x14001225f  mov     [r11+10h], rbx
0x140012263  push    rdi; int
0x140012264  sub     rsp, 20h
0x140012268  mov     rdi, rdx
0x14001226b  mov     qword ptr [r11+8], 0
0x140012273  mov     rcx, [rcx]
0x140012276  mov     rax, [rcx]
0x140012279  mov     qword ptr [r11+8], 0
0x140012281  lea     r8, [r11+8]
0x140012285  lea     rdx, _GUID_c9d9a725_786b_5113_b4b7_9b61764c220b
0x14001228c  mov     rax, [rax]
0x14001228f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012294  mov     ebx, eax
0x140012296  test    eax, eax
0x140012298  jns     short loc_1400122A1
0x14001229a  mov     edx, 1Dh
0x14001229f  jmp     short loc_1400122C0
0x1400122a1  mov     rcx, [rsp+28h+arg_0]
0x1400122a6  mov     rax, [rcx]
0x1400122a9  mov     rdx, rdi
0x1400122ac  mov     rax, [rax+38h]
0x1400122b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400122b5  mov     ebx, eax
0x1400122b7  test    eax, eax
0x1400122b9  jns     short loc_1400122D6
0x1400122bb  mov     edx, 1Fh; void *
0x1400122c0  lea     r8, aOnecoreWindows_4; "onecore\\windows\\directx\\database\\up"...
0x1400122c7  mov     r9d, eax; char *
0x1400122ca  mov     rcx, [rsp+28h]; this
0x1400122cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400122d4  jmp     short loc_1400122D8
0x1400122d6  xor     ebx, ebx
0x1400122d8  lea     rcx, [rsp+28h+arg_0]
0x1400122dd  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400122e2  mov     eax, ebx
0x1400122e4  mov     rbx, [rsp+28h+arg_8]
0x1400122e9  add     rsp, 20h
0x1400122ed  pop     rdi
0x1400122ee  retn
```
