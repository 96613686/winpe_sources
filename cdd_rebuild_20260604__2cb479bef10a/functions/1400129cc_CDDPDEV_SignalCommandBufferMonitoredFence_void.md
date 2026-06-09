# CDDPDEV::SignalCommandBufferMonitoredFence(void)

- ea: `0x1400129cc`
- end: `0x140012b59`
- name: `?SignalCommandBufferMonitoredFence@CDDPDEV@@QEAAJXZ`
- size: `397`
- prototype: `__int64 __fastcall(CDDPDEV *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010c2c`

## callees

- `0x1400129cc`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `watchdog!WdLogSingleEntry1` at `0x140012a51`
- `watchdog!WdLogSingleEntry1` at `0x140012ae4`
- `watchdog!WdLogSingleEntry1` at `0x140012a51`
- `watchdog!WdLogSingleEntry1` at `0x140012ae4`
- `watchdog!WdLogNewEntry5_WdError` at `0x140012a67`
- `watchdog!WdLogNewEntry5_WdError` at `0x140012afa`
- `watchdog!WdLogNewEntry5_WdError` at `0x140012a67`
- `watchdog!WdLogNewEntry5_WdError` at `0x140012afa`

## pseudocode

```c
__int64 __fastcall CDDPDEV::SignalCommandBufferMonitoredFence(CDDPDEV *this)
{
  char *v1; // rdi
  __int64 (__fastcall *v3)(_QWORD *); // rax
  int v4; // eax
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rax
  __int64 (__fastcall *v9)(_QWORD *); // rax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  _QWORD *v13; // rax
  _QWORD v15[10]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v16; // [rsp+80h] [rbp+10h] BYREF

  v1 = (char *)this + 12736;
  v16 = *((_QWORD *)this + 1594);
  if ( *((_DWORD *)this + 632) )
  {
    v15[1] = (char *)this + 2528;
    v15[4] = &v16;
    v9 = (__int64 (__fastcall *)(_QWORD *))*((_QWORD *)this + 59);
    v15[0] = 0x100000000LL;
    v15[2] = 1;
    v15[3] = (char *)this + 12736;
    v10 = v9(v15);
    v5 = v10;
    if ( v10 < 0 )
    {
      WdLogSingleEntry1(2, v10);
      WdLogGlobalForLineNumber = 1239;
      v13 = (_QWORD *)WdLogNewEntry5_WdError(v12, v11);
      v13[3] = gCddImageInfo;
      v13[4] = (unsigned int)dword_14003E570;
      v13[5] = 215857758;
      WdLogGlobalForLineNumber = 1239;
      goto LABEL_7;
    }
LABEL_6:
    *((_QWORD *)this + 1595) = *((_QWORD *)this + 1594);
    goto LABEL_7;
  }
  memset(v15, 0, sizeof(v15));
  LODWORD(v15[0]) = *((_DWORD *)this + 631);
  v15[2] = &v16;
  v3 = (__int64 (__fastcall *)(_QWORD *))*((_QWORD *)this + 58);
  HIDWORD(v15[0]) = 1;
  v15[1] = v1;
  v4 = v3(v15);
  v5 = v4;
  if ( v4 >= 0 )
    goto LABEL_6;
  WdLogSingleEntry1(2, v4);
  WdLogGlobalForLineNumber = 1223;
  v8 = (_QWORD *)WdLogNewEntry5_WdError(v7, v6);
  v8[3] = gCddImageInfo;
  v8[4] = (unsigned int)dword_14003E570;
  v8[5] = 215857758;
  WdLogGlobalForLineNumber = 1223;
LABEL_7:
  ++*((_QWORD *)this + 1594);
  return v5;
}

```

## disassembly

```asm
0x1400129cc  mov     [rsp-8+arg_8], rbx
0x1400129d1  mov     [rsp-8+arg_10], rdi
0x1400129d6  push    rbp
0x1400129d7  mov     rbp, rsp
0x1400129da  sub     rsp, 70h
0x1400129de  mov     rax, [rcx+31D0h]
0x1400129e5  lea     rdi, [rcx+31C0h]
0x1400129ec  mov     [rbp+arg_0], rax
0x1400129f0  mov     rbx, rcx
0x1400129f3  lea     rax, [rcx+9E0h]
0x1400129fa  cmp     dword ptr [rax], 0
0x1400129fd  jnz     loc_140012A9F
0x140012a03  xor     edx, edx; Val
0x140012a05  lea     rcx, [rbp+var_50]; void *
0x140012a09  lea     r8d, [rdx+50h]; Size
0x140012a0d  call    memset
0x140012a12  mov     eax, [rbx+9DCh]
0x140012a18  lea     rcx, [rbp+var_50]
0x140012a1c  mov     [rbp+var_50], eax
0x140012a1f  lea     rax, [rbp+arg_0]
0x140012a23  mov     [rbp+var_40], rax
0x140012a27  mov     rax, [rbx+1D0h]
0x140012a2e  mov     [rbp+var_4C], 1
0x140012a35  mov     [rbp+var_48], rdi
0x140012a39  call    _guard_dispatch_icall
0x140012a3e  movsxd  rdi, eax
0x140012a41  test    eax, eax
0x140012a43  jns     loc_140012B2F
0x140012a49  mov     rdx, rdi
0x140012a4c  mov     ecx, 2
0x140012a51  call    cs:__imp_WdLogSingleEntry1
0x140012a58  nop     dword ptr [rax+rax+00h]
0x140012a5d  mov     cs:WdLogGlobalForLineNumber, 4C7h
0x140012a67  call    cs:__imp_WdLogNewEntry5_WdError
0x140012a6e  nop     dword ptr [rax+rax+00h]
0x140012a73  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140012a7a  mov     [rax+18h], rcx
0x140012a7e  mov     ecx, cs:dword_14003E570
0x140012a84  mov     [rax+20h], rcx
0x140012a88  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140012a90  mov     cs:WdLogGlobalForLineNumber, 4C7h
0x140012a9a  jmp     loc_140012B3D
0x140012a9f  mov     [rbp+var_48], rax
0x140012aa3  lea     rax, [rbp+arg_0]
0x140012aa7  mov     [rbp+var_30], rax
0x140012aab  mov     rax, [rcx+1D8h]
0x140012ab2  lea     rcx, [rbp+var_50]
0x140012ab6  mov     [rbp+var_50], 0
0x140012abd  mov     [rbp+var_40], 1
0x140012ac5  mov     [rbp+var_4C], 1
0x140012acc  mov     [rbp+var_38], rdi
0x140012ad0  call    _guard_dispatch_icall
0x140012ad5  movsxd  rdi, eax
0x140012ad8  test    eax, eax
0x140012ada  jns     short loc_140012B2F
0x140012adc  mov     rdx, rdi
0x140012adf  mov     ecx, 2
0x140012ae4  call    cs:__imp_WdLogSingleEntry1
0x140012aeb  nop     dword ptr [rax+rax+00h]
0x140012af0  mov     cs:WdLogGlobalForLineNumber, 4D7h
0x140012afa  call    cs:__imp_WdLogNewEntry5_WdError
0x140012b01  nop     dword ptr [rax+rax+00h]
0x140012b06  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140012b0d  mov     [rax+18h], rcx
0x140012b11  mov     ecx, cs:dword_14003E570
0x140012b17  mov     [rax+20h], rcx
0x140012b1b  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140012b23  mov     cs:WdLogGlobalForLineNumber, 4D7h
0x140012b2d  jmp     short loc_140012B3D
0x140012b2f  mov     rax, [rbx+31D0h]
0x140012b36  mov     [rbx+31D8h], rax
0x140012b3d  inc     qword ptr [rbx+31D0h]
0x140012b44  lea     r11, [rsp+70h+var_s0]
0x140012b49  mov     rbx, [r11+18h]
0x140012b4d  mov     eax, edi
0x140012b4f  mov     rdi, [r11+20h]
0x140012b53  mov     rsp, r11
0x140012b56  pop     rbp
0x140012b57  retn
```
