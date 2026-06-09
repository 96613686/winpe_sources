# DafCreateImportExportContext

- ea: `0x18000a430`
- end: `0x18000a4a5`
- name: `DafCreateImportExportContext`
- size: `117`
- prototype: `__int64 __fastcall(struct _DAC_CLIENT_CONTEXT **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002284`
- `0x180002f10`
- `0x18000a430`
- `0x18000bbc2`

## pseudocode

```c
__int64 __fastcall DafCreateImportExportContext(struct _DAC_CLIENT_CONTEXT **a1)
{
  _DWORD v3[18]; // [rsp+20h] [rbp-48h] BYREF

  memset_0(v3, 0, 0x40u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1937730dad33375cdddf08c541dbf4f4_Traceguids);
  if ( !a1 )
    return 2147942487LL;
  *a1 = 0;
  v3[0] = 5;
  return CreateContext((struct _DAC_CREATE_CONTEXT_PARAMS *)v3, a1);
}

```

## disassembly

```asm
0x18000a430  push    rbx
0x18000a432  sub     rsp, 60h
0x18000a436  xor     edx, edx; Val
0x18000a438  mov     rbx, rcx
0x18000a43b  lea     rcx, [rsp+68h+var_48]; void *
0x18000a440  lea     r8d, [rdx+40h]; Size
0x18000a444  call    memset_0
0x18000a449  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a450  lea     rax, WPP_GLOBAL_Control
0x18000a457  cmp     rcx, rax
0x18000a45a  jz      short loc_18000A477
0x18000a45c  cmp     byte ptr [rcx+19h], 4
0x18000a460  jb      short loc_18000A477
0x18000a462  mov     rcx, [rcx+10h]
0x18000a466  lea     r8, WPP_1937730dad33375cdddf08c541dbf4f4_Traceguids
0x18000a46d  mov     edx, 0Ah
0x18000a472  call    WPP_SF_s
0x18000a477  test    rbx, rbx
0x18000a47a  jnz     short loc_18000A483
0x18000a47c  mov     eax, 80070057h
0x18000a481  jmp     short loc_18000A49F
0x18000a483  mov     rdx, rbx; struct _DAC_CLIENT_CONTEXT **
0x18000a486  mov     qword ptr [rbx], 0
0x18000a48d  lea     rcx, [rsp+68h+var_48]; struct _DAC_CREATE_CONTEXT_PARAMS *
0x18000a492  mov     [rsp+68h+var_48], 5
0x18000a49a  call    ?CreateContext@@YAJPEAU_DAC_CREATE_CONTEXT_PARAMS@@PEAPEAU_DAC_CLIENT_CONTEXT@@@Z; CreateContext(_DAC_CREATE_CONTEXT_PARAMS *,_DAC_CLIENT_CONTEXT * *)
0x18000a49f  add     rsp, 60h
0x18000a4a3  pop     rbx
0x18000a4a4  retn
```
