# FveEasUtil::I_GetFVEVolumeHandle(ushort const *,Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)

- ea: `0x1800179bc`
- end: `0x180017a38`
- name: `?I_GetFVEVolumeHandle@FveEasUtil@@CAJPEBGAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z`
- size: `124`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007360`
- `0x18000c924`
- `0x180015960`
- `0x180015d44`
- `0x180016c74`
- `0x1800178e8`
- `0x180017a40`
- `0x180017eac`
- `0x180023fe4`
- `0x18002868c`

## callees

- `0x1800037a0`
- `0x180005018`
- `0x1800179bc`

## import_xrefs

- `FVEAPI!FveOpenVolumeW` at `0x1800179e9`
- `FVEAPI!FveOpenVolumeW` at `0x1800179e9`

## pseudocode

```c
__int64 __fastcall FveEasUtil::I_GetFVEVolumeHandle(__int64 a1, __int64 a2, unsigned __int8 a3)
{
  int v4; // edi
  unsigned int v6; // ebx

  v4 = a3;
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(a2);
  v6 = FveOpenVolumeW(a1, v4 ^ 1u, a2 + 8);
  if ( v6 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800179bc  mov     [rsp+arg_0], rbx
0x1800179c1  mov     [rsp+arg_8], rsi
0x1800179c6  push    rdi
0x1800179c7  sub     rsp, 20h
0x1800179cb  mov     rsi, rcx
0x1800179ce  movzx   edi, r8b
0x1800179d2  mov     rcx, rdx
0x1800179d5  mov     rbx, rdx
0x1800179d8  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x1800179dd  mov     edx, edi
0x1800179df  lea     r8, [rbx+8]
0x1800179e3  xor     edx, 1
0x1800179e6  mov     rcx, rsi
0x1800179e9  call    cs:__imp_FveOpenVolumeW
0x1800179ef  mov     ebx, eax
0x1800179f1  test    eax, eax
0x1800179f3  jz      short loc_180017A26
0x1800179f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179fc  lea     rax, WPP_GLOBAL_Control
0x180017a03  cmp     rcx, rax
0x180017a06  jz      short loc_180017A26
0x180017a08  test    byte ptr [rcx+1Ch], 40h
0x180017a0c  jz      short loc_180017A26
0x180017a0e  mov     rcx, [rcx+10h]
0x180017a12  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180017a19  mov     edx, 4Ah ; 'J'
0x180017a1e  mov     r9d, ebx
0x180017a21  call    WPP_SF_d
0x180017a26  mov     rsi, [rsp+28h+arg_8]
0x180017a2b  mov     eax, ebx
0x180017a2d  mov     rbx, [rsp+28h+arg_0]
0x180017a32  add     rsp, 20h
0x180017a36  pop     rdi
0x180017a37  retn
```
