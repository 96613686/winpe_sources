# CDDPDEV::CreateResidencyState(void)

- ea: `0x14002cd8c`
- end: `0x14002cf53`
- name: `?CreateResidencyState@CDDPDEV@@QEAAJXZ`
- size: `455`
- prototype: `__int64 __fastcall(CDDPDEV *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140021d5c`

## callees

- `0x14002cd8c`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x14002ce65`
- `watchdog!WdLogSingleEntry2` at `0x14002cf19`
- `watchdog!WdLogSingleEntry2` at `0x14002ce65`
- `watchdog!WdLogSingleEntry2` at `0x14002cf19`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002ce7c`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002ce7c`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002cdcc`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002cdcc`
- `watchdog!WdLogSingleEntry0` at `0x14002cdb5`
- `watchdog!WdLogSingleEntry0` at `0x14002cdb5`

## pseudocode

```c
__int64 __fastcall CDDPDEV::CreateResidencyState(CDDPDEV *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  _QWORD *v4; // rax
  __int64 (__fastcall *v5)(_DWORD *); // rax
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // ebx
  _QWORD *v11; // rax
  __int64 (__fastcall *v12)(_QWORD *); // rax
  int v13; // eax
  _DWORD v15[2]; // [rsp+20h] [rbp-49h] BYREF
  __int128 v16; // [rsp+28h] [rbp-41h]
  __int64 v17; // [rsp+38h] [rbp-31h]
  _QWORD v18[16]; // [rsp+40h] [rbp-29h] BYREF

  if ( !*((_DWORD *)this + 630) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1324;
    v4 = (_QWORD *)WdLogNewEntry5_WdAssertion(v3, v2);
    v4[3] = gCddImageInfo;
    v4[4] = (unsigned int)dword_14003E570;
    v4[5] = 215857758;
    WdLogGlobalForLineNumber = 1324;
  }
  v15[0] = *((_DWORD *)this + 630);
  v5 = (__int64 (__fastcall *)(_DWORD *))*((_QWORD *)this + 60);
  *((_QWORD *)this + 1594) = 1;
  *((_QWORD *)this + 1595) = 0;
  *((_QWORD *)this + 1596) = 0;
  *((_QWORD *)this + 1597) = 0;
  v16 = 0;
  v17 = 0;
  v15[1] = 0;
  v6 = v5(v15);
  v7 = v6;
  if ( v6 >= 0 )
  {
    *((_OWORD *)this + 795) = v16;
    memset(v18, 0, 0x60u);
    LODWORD(v18[0]) = *((_DWORD *)this + 630);
    v12 = (__int64 (__fastcall *)(_QWORD *))*((_QWORD *)this + 44);
    LODWORD(v18[1]) = 5;
    v18[2] = 0;
    LODWORD(v18[5]) = 0;
    v13 = v12(v18);
    v7 = v13;
    if ( v13 >= 0 )
    {
      *((_DWORD *)this + 3184) = v18[11];
      *((_QWORD *)this + 1593) = v18[3];
      return v7;
    }
    WdLogSingleEntry2(2, this, v13);
    v10 = 1367;
  }
  else
  {
    WdLogSingleEntry2(2, this, v6);
    v10 = 1346;
  }
  WdLogGlobalForLineNumber = v10;
  v11 = (_QWORD *)WdLogNewEntry5_WdError(v9, v8);
  v11[3] = gCddImageInfo;
  v11[4] = (unsigned int)dword_14003E570;
  v11[5] = 215857758;
  WdLogGlobalForLineNumber = v10;
  return v7;
}

```

## disassembly

```asm
0x14002cd8c  push    rbp
0x14002cd8e  push    rbx
0x14002cd8f  push    rdi
0x14002cd90  push    r14
0x14002cd92  lea     rbp, [rsp-3Fh]
0x14002cd97  sub     rsp, 0A8h
0x14002cd9e  cmp     dword ptr [rcx+9D8h], 0
0x14002cda5  mov     rbx, rcx
0x14002cda8  mov     r14d, 0CDDBA5Eh
0x14002cdae  jnz     short loc_14002CDF7
0x14002cdb0  mov     ecx, 1
0x14002cdb5  call    cs:__imp_WdLogSingleEntry0
0x14002cdbc  nop     dword ptr [rax+rax+00h]
0x14002cdc1  mov     edi, 52Ch
0x14002cdc6  mov     cs:WdLogGlobalForLineNumber, edi
0x14002cdcc  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002cdd3  nop     dword ptr [rax+rax+00h]
0x14002cdd8  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002cddf  mov     [rax+18h], rcx
0x14002cde3  mov     ecx, cs:dword_14003E570
0x14002cde9  mov     [rax+20h], rcx
0x14002cded  mov     [rax+28h], r14
0x14002cdf1  mov     cs:WdLogGlobalForLineNumber, edi
0x14002cdf7  mov     eax, [rbx+9D8h]
0x14002cdfd  lea     rcx, [rbp+57h+var_A0]
0x14002ce01  mov     [rbp+57h+var_A0], eax
0x14002ce04  xorps   xmm0, xmm0
0x14002ce07  mov     rax, [rbx+1E0h]
0x14002ce0e  mov     qword ptr [rbx+31D0h], 1
0x14002ce19  mov     qword ptr [rbx+31D8h], 0
0x14002ce24  mov     qword ptr [rbx+31E0h], 0
0x14002ce2f  mov     qword ptr [rbx+31E8h], 0
0x14002ce3a  movdqu  [rbp+57h+var_98], xmm0
0x14002ce3f  mov     [rbp+57h+var_88], 0
0x14002ce47  mov     [rbp+57h+var_9C], 0
0x14002ce4e  call    _guard_dispatch_icall
0x14002ce53  movsxd  rdi, eax
0x14002ce56  test    eax, eax
0x14002ce58  jns     short loc_14002CEAC
0x14002ce5a  mov     r8, rdi
0x14002ce5d  mov     rdx, rbx
0x14002ce60  mov     ecx, 2
0x14002ce65  call    cs:__imp_WdLogSingleEntry2
0x14002ce6c  nop     dword ptr [rax+rax+00h]
0x14002ce71  mov     ebx, 542h
0x14002ce76  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002ce7c  call    cs:__imp_WdLogNewEntry5_WdError
0x14002ce83  nop     dword ptr [rax+rax+00h]
0x14002ce88  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002ce8f  mov     [rax+18h], rcx
0x14002ce93  mov     ecx, cs:dword_14003E570
0x14002ce99  mov     [rax+20h], rcx
0x14002ce9d  mov     [rax+28h], r14
0x14002cea1  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002cea7  jmp     loc_14002CF43
0x14002ceac  mov     eax, dword ptr [rbp+57h+var_98]
0x14002ceaf  lea     rcx, [rbp+57h+var_80]; void *
0x14002ceb3  mov     [rbx+31B0h], eax
0x14002ceb9  xor     edx, edx; Val
0x14002cebb  mov     eax, dword ptr [rbp+57h+var_98+4]
0x14002cebe  mov     [rbx+31B4h], eax
0x14002cec4  mov     rax, qword ptr [rbp+57h+var_98+8]
0x14002cec8  lea     r8d, [rdx+60h]; Size
0x14002cecc  mov     [rbx+31B8h], rax
0x14002ced3  call    memset
0x14002ced8  mov     eax, [rbx+9D8h]
0x14002cede  lea     rcx, [rbp+57h+var_80]
0x14002cee2  mov     [rbp+57h+var_80], eax
0x14002cee5  mov     rax, [rbx+160h]
0x14002ceec  mov     [rbp+57h+var_78], 5
0x14002cef3  mov     [rbp+57h+var_70], 0
0x14002cefb  mov     [rbp+57h+var_58], 0
0x14002cf02  call    _guard_dispatch_icall
0x14002cf07  movsxd  rdi, eax
0x14002cf0a  test    eax, eax
0x14002cf0c  jns     short loc_14002CF2F
0x14002cf0e  mov     r8, rdi
0x14002cf11  mov     rdx, rbx
0x14002cf14  mov     ecx, 2
0x14002cf19  call    cs:__imp_WdLogSingleEntry2
0x14002cf20  nop     dword ptr [rax+rax+00h]
0x14002cf25  mov     ebx, 557h
0x14002cf2a  jmp     loc_14002CE76
0x14002cf2f  mov     eax, [rbp+57h+var_28]
0x14002cf32  mov     [rbx+31C0h], eax
0x14002cf38  mov     rax, [rbp+57h+var_68]
0x14002cf3c  mov     [rbx+31C8h], rax
0x14002cf43  mov     eax, edi
0x14002cf45  add     rsp, 0A8h
0x14002cf4c  pop     r14
0x14002cf4e  pop     rdi
0x14002cf4f  pop     rbx
0x14002cf50  pop     rbp
0x14002cf51  retn
```
