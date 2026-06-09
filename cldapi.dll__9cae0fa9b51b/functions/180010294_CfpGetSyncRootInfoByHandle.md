# CfpGetSyncRootInfoByHandle

- ea: `0x180010294`
- end: `0x180010354`
- name: `CfpGetSyncRootInfoByHandle`
- size: `192`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, __int64)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180004dd0`
- `0x1800064e0`
- `0x1800078d0`
- `0x180007f30`
- `0x18000e250`
- `0x1800100a0`
- `0x18001035c`
- `0x180012c28`

## callees

- `0x18000231e`
- `0x180010294`
- `0x18001cd74`

## pseudocode

```c
__int64 __fastcall CfpGetSyncRootInfoByHandle(unsigned __int64 hFile, int a2, void *a3, DWORD a4, DWORD *a5)
{
  int v9; // ebx
  __int64 result; // rax
  int v11; // [rsp+40h] [rbp-C8h] BYREF
  int v12[49]; // [rsp+44h] [rbp-C4h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+118h] [rbp+10h] BYREF

  memset_0(v12, 0, 0x94u);
  NumberOfBytesTransferred = 0;
  v11 = -1879048166;
  if ( a2 )
  {
    v9 = a2 - 1;
    if ( v9 )
    {
      if ( v9 != 1 )
        return 2147942487LL;
      v12[0] = -1073741818;
    }
    else
    {
      v12[0] = -1073741817;
    }
  }
  else
  {
    v12[0] = -1073741819;
  }
  result = IssueHsmControl(hFile, &v11, 0x98u, a3, a4, &NumberOfBytesTransferred, 0);
  if ( a5 )
    *a5 = NumberOfBytesTransferred;
  return result;
}

```

## disassembly

```asm
0x180010294  push    rbx
0x180010296  push    rbp
0x180010297  push    rsi
0x180010298  push    rdi
0x180010299  sub     rsp, 0E8h
0x1800102a0  mov     rsi, r8
0x1800102a3  mov     ebx, edx
0x1800102a5  mov     rbp, rcx
0x1800102a8  xor     edx, edx; Val
0x1800102aa  mov     r8d, 94h; Size
0x1800102b0  lea     rcx, [rsp+108h+var_C4]; void *
0x1800102b5  mov     edi, r9d
0x1800102b8  call    memset_0
0x1800102bd  mov     [rsp+108h+NumberOfBytesTransferred], 0
0x1800102c8  mov     [rsp+108h+var_C8], 9000001Ah
0x1800102d0  test    ebx, ebx
0x1800102d2  jz      short loc_1800102F9
0x1800102d4  sub     ebx, 1
0x1800102d7  jz      short loc_1800102EF
0x1800102d9  cmp     ebx, 1
0x1800102dc  jz      short loc_1800102E5
0x1800102de  mov     eax, 80070057h
0x1800102e3  jmp     short loc_180010347
0x1800102e5  mov     [rsp+108h+var_C4], 0C0000006h
0x1800102ed  jmp     short loc_180010301
0x1800102ef  mov     [rsp+108h+var_C4], 0C0000007h
0x1800102f7  jmp     short loc_180010301
0x1800102f9  mov     [rsp+108h+var_C4], 0C0000005h
0x180010301  lea     rax, [rsp+108h+NumberOfBytesTransferred]
0x180010309  mov     [rsp+108h+var_D8], 0; __int64
0x180010312  mov     [rsp+108h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180010317  lea     rdx, [rsp+108h+var_C8]
0x18001031c  mov     r9, rsi
0x18001031f  mov     [rsp+108h+var_E8], edi; DWORD
0x180010323  mov     r8d, 98h
0x180010329  mov     rcx, rbp; hFile
0x18001032c  call    IssueHsmControl
0x180010331  mov     rdx, [rsp+108h+arg_20]
0x180010339  test    rdx, rdx
0x18001033c  jz      short loc_180010347
0x18001033e  mov     ecx, [rsp+108h+NumberOfBytesTransferred]
0x180010345  mov     [rdx], ecx
0x180010347  add     rsp, 0E8h
0x18001034e  pop     rdi
0x18001034f  pop     rsi
0x180010350  pop     rbp
0x180010351  pop     rbx
0x180010352  retn
```
