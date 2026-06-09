# RasCreateConnection

- ea: `0x180016d50`
- end: `0x180016e87`
- name: `RasCreateConnection`
- size: `311`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, unsigned int, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180002f80`
- `0x180016d50`
- `0x180020fd8`
- `0x180021000`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016d9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016d9a`

## pseudocode

```c
__int64 __fastcall RasCreateConnection(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  DWORD CurrentProcessId; // eax
  unsigned int v16; // eax
  unsigned int v17; // ebx
  PVOID *v18; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 378, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  CurrentProcessId = GetCurrentProcessId();
  v16 = SubmitLocalRequest(0x35u, CurrentProcessId, a2, a5, a6, a7, a8, a9, a10, a11, a1, a3, a4);
  v17 = v16;
  if ( !v16 )
    goto LABEL_10;
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v17;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 379, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v16);
LABEL_10:
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 && *((_BYTE *)v18 + 25) >= 6u )
    WPP_SF_d(v18[2], 380, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v17);
  return v17;
}

```

## disassembly

```asm
0x180016d50  push    rbx
0x180016d52  push    rbp
0x180016d53  push    rsi
0x180016d54  push    rdi
0x180016d55  push    r15
0x180016d57  sub     rsp, 70h
0x180016d5b  mov     rbx, r9
0x180016d5e  mov     rdi, r8
0x180016d61  mov     esi, edx
0x180016d63  mov     rbp, rcx
0x180016d66  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d6d  lea     r15, WPP_GLOBAL_Control
0x180016d74  cmp     rcx, r15
0x180016d77  jz      short loc_180016D9A
0x180016d79  test    byte ptr [rcx+1Ch], 40h
0x180016d7d  jz      short loc_180016D9A
0x180016d7f  cmp     byte ptr [rcx+19h], 6
0x180016d83  jb      short loc_180016D9A
0x180016d85  mov     rcx, [rcx+10h]
0x180016d89  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180016d90  mov     edx, 17Ah
0x180016d95  call    WPP_SF_
0x180016d9a  call    cs:__imp_GetCurrentProcessId
0x180016da0  mov     r9d, [rsp+98h+arg_20]
0x180016da8  mov     ecx, 35h ; '5'
0x180016dad  mov     [rsp+98h+var_38], rbx
0x180016db2  mov     edx, eax
0x180016db4  mov     rax, [rsp+98h+arg_50]
0x180016dbc  mov     r8d, esi
0x180016dbf  mov     [rsp+98h+var_40], rdi
0x180016dc4  mov     [rsp+98h+var_48], rbp
0x180016dc9  mov     [rsp+98h+var_50], rax
0x180016dce  mov     rax, [rsp+98h+arg_48]
0x180016dd6  mov     [rsp+98h+var_58], rax
0x180016ddb  mov     rax, [rsp+98h+arg_40]
0x180016de3  mov     [rsp+98h+var_60], rax
0x180016de8  mov     rax, [rsp+98h+arg_38]
0x180016df0  mov     [rsp+98h+var_68], rax
0x180016df5  mov     rax, [rsp+98h+arg_30]
0x180016dfd  mov     [rsp+98h+var_70], rax
0x180016e02  mov     rax, [rsp+98h+arg_28]
0x180016e0a  mov     [rsp+98h+var_78], rax
0x180016e0f  call    SubmitLocalRequest
0x180016e14  mov     ebx, eax
0x180016e16  test    eax, eax
0x180016e18  jz      short loc_180016E4A
0x180016e1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e21  cmp     rcx, r15
0x180016e24  jz      short loc_180016E7A
0x180016e26  test    byte ptr [rcx+1Ch], 40h
0x180016e2a  jz      short loc_180016E51
0x180016e2c  cmp     byte ptr [rcx+19h], 2
0x180016e30  jb      short loc_180016E51
0x180016e32  mov     rcx, [rcx+10h]
0x180016e36  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180016e3d  mov     edx, 17Bh
0x180016e42  mov     r9d, eax
0x180016e45  call    WPP_SF_d
0x180016e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e51  cmp     rcx, r15
0x180016e54  jz      short loc_180016E7A
0x180016e56  test    byte ptr [rcx+1Ch], 40h
0x180016e5a  jz      short loc_180016E7A
0x180016e5c  cmp     byte ptr [rcx+19h], 6
0x180016e60  jb      short loc_180016E7A
0x180016e62  mov     rcx, [rcx+10h]
0x180016e66  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180016e6d  mov     edx, 17Ch
0x180016e72  mov     r9d, ebx
0x180016e75  call    WPP_SF_d
0x180016e7a  mov     eax, ebx
0x180016e7c  add     rsp, 70h
0x180016e80  pop     r15
0x180016e82  pop     rdi
0x180016e83  pop     rsi
0x180016e84  pop     rbp
0x180016e85  pop     rbx
0x180016e86  retn
```
