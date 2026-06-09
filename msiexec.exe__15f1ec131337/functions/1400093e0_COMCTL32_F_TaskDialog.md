# COMCTL32::F_TaskDialog

- ea: `0x1400093e0`
- end: `0x140009467`
- name: `COMCTL32::F_TaskDialog`
- size: `135`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x140008d60`
- `0x1400093e0`
- `0x14000a010`

## string_xrefs

- `0x1400093f9`: `TaskDialog`

## pseudocode

```c
__int64 __fastcall COMCTL32::F_TaskDialog(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  if ( Bind_COMCTL32("TaskDialog", &COMCTL32::TaskDialog) )
    return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64, __int64, int, __int64, __int64))COMCTL32::TaskDialog)(
             a1,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7,
             a8);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x1400093e0  push    rbx
0x1400093e2  push    rbp
0x1400093e3  push    rsi
0x1400093e4  push    rdi
0x1400093e5  sub     rsp, 58h
0x1400093e9  mov     rsi, rdx
0x1400093ec  mov     rbp, rcx
0x1400093ef  lea     rdx, ?TaskDialog@COMCTL32@@3P6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBG22K2PEAH@ZEA; __int64 (**)(void)
0x1400093f6  mov     rbx, r9
0x1400093f9  lea     rcx, aTaskdialog; "TaskDialog"
0x140009400  mov     rdi, r8
0x140009403  call    ?Bind_COMCTL32@@YAP6A_JXZPEBDPEAP6A_JXZ@Z; Bind_COMCTL32(char const *,__int64 (**)(void))
0x140009408  test    rax, rax
0x14000940b  jz      short loc_140009459
0x14000940d  mov     r9, [rsp+78h+arg_38]
0x140009415  mov     r8, rdi
0x140009418  mov     rdx, [rsp+78h+arg_30]
0x140009420  mov     ecx, [rsp+78h+arg_28]
0x140009427  mov     rax, cs:?TaskDialog@COMCTL32@@3P6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBG22K2PEAH@ZEA; long (*COMCTL32::TaskDialog)(HWND__ *,HINSTANCE__ *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,int *)
0x14000942e  mov     [rsp+78h+var_40], r9
0x140009433  mov     r9, rbx
0x140009436  mov     [rsp+78h+var_48], rdx
0x14000943b  mov     rdx, rsi
0x14000943e  mov     [rsp+78h+var_50], ecx
0x140009442  mov     rcx, [rsp+78h+arg_20]
0x14000944a  mov     [rsp+78h+var_58], rcx
0x14000944f  mov     rcx, rbp
0x140009452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009457  jmp     short loc_14000945E
0x140009459  mov     eax, 80004005h
0x14000945e  add     rsp, 58h
0x140009462  pop     rdi
0x140009463  pop     rsi
0x140009464  pop     rbp
0x140009465  pop     rbx
0x140009466  retn
```
