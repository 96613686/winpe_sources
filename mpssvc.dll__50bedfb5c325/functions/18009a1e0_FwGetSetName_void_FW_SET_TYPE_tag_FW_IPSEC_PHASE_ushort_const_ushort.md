# FwGetSetName(void *,FW_SET_TYPE,_tag_FW_IPSEC_PHASE,ushort const *,ushort * *)

- ea: `0x18009a1e0`
- end: `0x18009a33f`
- name: `?FwGetSetName@@YAJPEAXW4FW_SET_TYPE@@W4_tag_FW_IPSEC_PHASE@@PEBGPEAPEAG@Z`
- size: `351`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18009e51c`
- `0x18009edb8`

## callees

- `0x1800729c0`
- `0x18009a1e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009a287`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009a2b8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009a287`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009a2b8`
- `fwbase!FwStringCopy` at `0x18009a29e`
- `fwbase!FwStringCopy` at `0x18009a2e4`
- `fwbase!FwStringCopy` at `0x18009a29e`
- `fwbase!FwStringCopy` at `0x18009a2e4`
- `fwbase!FwReportReturnError` at `0x18009a254`
- `fwbase!FwReportReturnError` at `0x18009a312`
- `fwbase!FwReportReturnError` at `0x18009a254`
- `fwbase!FwReportReturnError` at `0x18009a312`
- `FWPolicyIOMgr!FwFreeSets` at `0x18009a2f9`
- `FWPolicyIOMgr!FwFreeSets` at `0x18009a2f9`
- `FWPolicyIOMgr!FwEnumSets` at `0x18009a239`
- `FWPolicyIOMgr!FwEnumSets` at `0x18009a239`

## pseudocode

```c
__int64 __fastcall FwGetSetName(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v6; // ebp
  int v7; // eax
  int v8; // ebx
  unsigned int v9; // edx
  int v10; // r14d
  _QWORD *v11; // rdi
  int v12; // esi
  _QWORD *v14; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v15; // [rsp+48h] [rbp-50h] BYREF

  v6 = a2;
  v14 = 0;
  v15 = 0;
  v7 = FwEnumSets(a1, a2, a3, &v14, &v15, 196608, 0);
  v8 = v7;
  if ( v7 < 0 )
  {
    FwReportReturnError("FwGetSetName", (unsigned int)v7);
    goto LABEL_14;
  }
  v9 = v15;
  v10 = 0;
  v11 = v14;
  v12 = 0;
  if ( v15 )
  {
    while ( v6 )
    {
      if ( v6 == 1 )
      {
        if ( !(unsigned int)_o__wcsicmp(v11[2], a4) )
        {
          v8 = FwStringCopy(v11[3], a5);
          v10 = 1;
        }
LABEL_9:
        if ( v10 == 1 )
          goto LABEL_14;
        v9 = v15;
      }
      v11 = (_QWORD *)*v11;
      if ( ++v12 >= v9 )
        goto LABEL_14;
    }
    if ( !(unsigned int)_o__wcsicmp(v11[2], a4) )
    {
      v8 = FwStringCopy(v11[3], a5);
      goto LABEL_14;
    }
    goto LABEL_9;
  }
LABEL_14:
  FwFreeSets(v14, v6);
  if ( v8 < 0 )
    return (unsigned int)FwReportReturnError("FwGetSetName", (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18009a1e0  mov     r11, rsp
0x18009a1e3  push    rbx
0x18009a1e4  push    rbp
0x18009a1e5  push    rsi
0x18009a1e6  push    rdi
0x18009a1e7  push    r12
0x18009a1e9  push    r14
0x18009a1eb  push    r15
0x18009a1ed  sub     rsp, 60h
0x18009a1f1  mov     rax, cs:__security_cookie
0x18009a1f8  xor     rax, rsp
0x18009a1fb  mov     [rsp+98h+var_48], rax
0x18009a200  mov     r15, [rsp+98h+arg_20]
0x18009a208  lea     rax, [r11-50h]
0x18009a20c  mov     r12, r9
0x18009a20f  mov     [rsp+98h+var_68], 0
0x18009a217  mov     [rsp+98h+var_70], 30000h
0x18009a21f  lea     r9, [r11-58h]
0x18009a223  mov     [r11-78h], rax
0x18009a227  mov     ebp, edx
0x18009a229  mov     qword ptr [r11-58h], 0
0x18009a231  mov     [rsp+98h+var_50], 0
0x18009a239  call    cs:__imp_FwEnumSets
0x18009a240  nop     dword ptr [rax+rax+00h]
0x18009a245  mov     ebx, eax
0x18009a247  test    eax, eax
0x18009a249  jns     short loc_18009A265
0x18009a24b  mov     edx, eax
0x18009a24d  lea     rcx, aFwgetsetname; "FwGetSetName"
0x18009a254  call    cs:__imp_FwReportReturnError
0x18009a25b  nop     dword ptr [rax+rax+00h]
0x18009a260  jmp     loc_18009A2F2
0x18009a265  mov     edx, [rsp+98h+var_50]
0x18009a269  xor     r14d, r14d
0x18009a26c  mov     rdi, [rsp+98h+var_58]
0x18009a271  xor     esi, esi
0x18009a273  test    edx, edx
0x18009a275  jz      short loc_18009A2F2
0x18009a277  test    ebp, ebp
0x18009a279  jz      short loc_18009A2B1
0x18009a27b  cmp     ebp, 1
0x18009a27e  jnz     short loc_18009A2D2
0x18009a280  mov     rcx, [rdi+10h]
0x18009a284  mov     rdx, r12
0x18009a287  call    cs:__imp__o__wcsicmp
0x18009a28e  nop     dword ptr [rax+rax+00h]
0x18009a293  test    eax, eax
0x18009a295  jnz     short loc_18009A2C8
0x18009a297  mov     rcx, [rdi+18h]
0x18009a29b  mov     rdx, r15
0x18009a29e  call    cs:__imp_FwStringCopy
0x18009a2a5  nop     dword ptr [rax+rax+00h]
0x18009a2aa  mov     ebx, eax
0x18009a2ac  mov     r14d, ebp
0x18009a2af  jmp     short loc_18009A2C8
0x18009a2b1  mov     rcx, [rdi+10h]
0x18009a2b5  mov     rdx, r12
0x18009a2b8  call    cs:__imp__o__wcsicmp
0x18009a2bf  nop     dword ptr [rax+rax+00h]
0x18009a2c4  test    eax, eax
0x18009a2c6  jz      short loc_18009A2DD
0x18009a2c8  cmp     r14d, 1
0x18009a2cc  jz      short loc_18009A2F2
0x18009a2ce  mov     edx, [rsp+98h+var_50]
0x18009a2d2  mov     rdi, [rdi]
0x18009a2d5  inc     esi
0x18009a2d7  cmp     esi, edx
0x18009a2d9  jb      short loc_18009A277
0x18009a2db  jmp     short loc_18009A2F2
0x18009a2dd  mov     rcx, [rdi+18h]
0x18009a2e1  mov     rdx, r15
0x18009a2e4  call    cs:__imp_FwStringCopy
0x18009a2eb  nop     dword ptr [rax+rax+00h]
0x18009a2f0  mov     ebx, eax
0x18009a2f2  mov     rcx, [rsp+98h+var_58]
0x18009a2f7  mov     edx, ebp
0x18009a2f9  call    cs:__imp_FwFreeSets
0x18009a300  nop     dword ptr [rax+rax+00h]
0x18009a305  test    ebx, ebx
0x18009a307  jns     short loc_18009A320
0x18009a309  mov     edx, ebx
0x18009a30b  lea     rcx, aFwgetsetname; "FwGetSetName"
0x18009a312  call    cs:__imp_FwReportReturnError
0x18009a319  nop     dword ptr [rax+rax+00h]
0x18009a31e  mov     ebx, eax
0x18009a320  mov     eax, ebx
0x18009a322  mov     rcx, [rsp+98h+var_48]
0x18009a327  xor     rcx, rsp; StackCookie
0x18009a32a  call    __security_check_cookie
0x18009a32f  add     rsp, 60h
0x18009a333  pop     r15
0x18009a335  pop     r14
0x18009a337  pop     r12
0x18009a339  pop     rdi
0x18009a33a  pop     rsi
0x18009a33b  pop     rbp
0x18009a33c  pop     rbx
0x18009a33d  retn
```
