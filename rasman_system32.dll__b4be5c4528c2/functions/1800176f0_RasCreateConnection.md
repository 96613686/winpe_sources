# RasCreateConnection

- ea: `0x1800176f0`
- end: `0x18001782e`
- name: `RasCreateConnection`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1800030d0`
- `0x1800176f0`
- `0x180021ae4`
- `0x180021b14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001773a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001773a`

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
0x1800176f0  push    rbx
0x1800176f2  push    rbp
0x1800176f3  push    rsi
0x1800176f4  push    rdi
0x1800176f5  push    r15
0x1800176f7  sub     rsp, 70h
0x1800176fb  mov     rbx, r9
0x1800176fe  mov     rdi, r8
0x180017701  mov     esi, edx
0x180017703  mov     rbp, rcx
0x180017706  mov     rcx, cs:WPP_GLOBAL_Control
0x18001770d  lea     r15, WPP_GLOBAL_Control
0x180017714  cmp     rcx, r15
0x180017717  jz      short loc_18001773A
0x180017719  test    byte ptr [rcx+1Ch], 40h
0x18001771d  jz      short loc_18001773A
0x18001771f  cmp     byte ptr [rcx+19h], 6
0x180017723  jb      short loc_18001773A
0x180017725  mov     rcx, [rcx+10h]
0x180017729  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180017730  mov     edx, 17Ah
0x180017735  call    WPP_SF_
0x18001773a  call    cs:__imp_GetCurrentProcessId
0x180017741  nop     dword ptr [rax+rax+00h]
0x180017746  mov     r9d, [rsp+98h+arg_20]
0x18001774e  mov     ecx, 35h ; '5'
0x180017753  mov     [rsp+98h+var_38], rbx
0x180017758  mov     edx, eax
0x18001775a  mov     rax, [rsp+98h+arg_50]
0x180017762  mov     r8d, esi
0x180017765  mov     [rsp+98h+var_40], rdi
0x18001776a  mov     [rsp+98h+var_48], rbp
0x18001776f  mov     [rsp+98h+var_50], rax
0x180017774  mov     rax, [rsp+98h+arg_48]
0x18001777c  mov     [rsp+98h+var_58], rax
0x180017781  mov     rax, [rsp+98h+arg_40]
0x180017789  mov     [rsp+98h+var_60], rax
0x18001778e  mov     rax, [rsp+98h+arg_38]
0x180017796  mov     [rsp+98h+var_68], rax
0x18001779b  mov     rax, [rsp+98h+arg_30]
0x1800177a3  mov     [rsp+98h+var_70], rax
0x1800177a8  mov     rax, [rsp+98h+arg_28]
0x1800177b0  mov     [rsp+98h+var_78], rax
0x1800177b5  call    SubmitLocalRequest
0x1800177ba  mov     ebx, eax
0x1800177bc  test    eax, eax
0x1800177be  jz      short loc_1800177F0
0x1800177c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177c7  cmp     rcx, r15
0x1800177ca  jz      short loc_180017820
0x1800177cc  test    byte ptr [rcx+1Ch], 40h
0x1800177d0  jz      short loc_1800177F7
0x1800177d2  cmp     byte ptr [rcx+19h], 2
0x1800177d6  jb      short loc_1800177F7
0x1800177d8  mov     rcx, [rcx+10h]
0x1800177dc  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800177e3  mov     edx, 17Bh
0x1800177e8  mov     r9d, eax
0x1800177eb  call    WPP_SF_d
0x1800177f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177f7  cmp     rcx, r15
0x1800177fa  jz      short loc_180017820
0x1800177fc  test    byte ptr [rcx+1Ch], 40h
0x180017800  jz      short loc_180017820
0x180017802  cmp     byte ptr [rcx+19h], 6
0x180017806  jb      short loc_180017820
0x180017808  mov     rcx, [rcx+10h]
0x18001780c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180017813  mov     edx, 17Ch
0x180017818  mov     r9d, ebx
0x18001781b  call    WPP_SF_d
0x180017820  mov     eax, ebx
0x180017822  add     rsp, 70h
0x180017826  pop     r15
0x180017828  pop     rdi
0x180017829  pop     rsi
0x18001782a  pop     rbp
0x18001782b  pop     rbx
0x18001782c  retn
```
