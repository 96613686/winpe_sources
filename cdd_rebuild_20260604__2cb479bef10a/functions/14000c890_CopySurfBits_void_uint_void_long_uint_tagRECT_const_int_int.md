# CopySurfBits(void *,uint,void *,long,uint,tagRECT const *,int,int)

- ea: `0x14000c890`
- end: `0x14000c9f0`
- name: `?CopySurfBits@@YAXPEAXI0JIPEBUtagRECT@@HH@Z`
- size: `352`
- prototype: `void __fastcall(void *, unsigned int, void *, int, unsigned int, const struct tagRECT *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a254`

## callees

- `0x14000c890`

## import_xrefs

- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x14000c939`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x14000c939`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14000c9a2`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14000c9a2`
- `watchdog!WdLogSingleEntry0` at `0x14000c98c`
- `watchdog!WdLogSingleEntry0` at `0x14000c98c`

## pseudocode

```c
void __fastcall CopySurfBits(char *a1, unsigned int a2, char *a3, int a4, unsigned int a5, const struct tagRECT *a6)
{
  __int64 v6; // r15
  char *v7; // r10
  __int64 v8; // r12
  char *v9; // r11
  int i; // ebx
  LONG top; // edx
  unsigned int v12; // r9d
  SIZE_T v13; // r8
  __int64 v14; // rcx
  char *v15; // rsi
  char *v16; // r14
  unsigned int j; // edi
  unsigned int v20; // [rsp+90h] [rbp+28h]
  int v22; // [rsp+A0h] [rbp+38h]

  v6 = a4;
  v7 = a3;
  v8 = a2;
  v9 = a1;
  for ( i = 0; !i; i = 1 )
  {
    top = a6->top;
    v12 = a6->bottom - top;
    v22 = v12;
    v13 = (unsigned int)(4 * (a6->right - a6->left));
    v20 = 4 * (a6->right - a6->left);
    v14 = (unsigned int)(4 * a6->left);
    v15 = &v9[v14 + (unsigned int)(v8 * top)];
    v16 = &v7[v14 + (int)v6 * top];
    for ( j = 0; j < v12; ++j )
    {
      RtlCopyMemoryNonTemporal(v15, v16, v13);
      v15 += v8;
      v16 += v6;
      v13 = v20;
      v12 = v22;
    }
    v7 = a3;
    v9 = a1;
  }
}

```

## disassembly

```asm
0x14000c890  mov     rax, rsp
0x14000c893  mov     [rax+10h], rbx
0x14000c897  mov     [rax+20h], rsi
0x14000c89b  mov     [rax+18h], r8
0x14000c89f  mov     [rax+8], rcx
0x14000c8a3  push    rdi
0x14000c8a4  push    r12
0x14000c8a6  push    r13
0x14000c8a8  push    r14
0x14000c8aa  push    r15
0x14000c8ac  sub     rsp, 40h
0x14000c8b0  movsxd  r15, r9d
0x14000c8b3  mov     r10, r8
0x14000c8b6  mov     r12d, edx
0x14000c8b9  mov     r11, rcx
0x14000c8bc  xor     ebx, ebx
0x14000c8be  mov     r13, [rsp+68h+arg_28]
0x14000c8c6  jmp     loc_14000C978
0x14000c8cb  mov     eax, ebx
0x14000c8cd  add     rax, rax
0x14000c8d0  mov     ecx, [r13+rax*8+0]
0x14000c8d5  mov     edx, [r13+rax*8+4]
0x14000c8da  mov     r9d, [r13+rax*8+0Ch]
0x14000c8df  sub     r9d, edx
0x14000c8e2  mov     [rsp+68h+arg_30], r9d
0x14000c8ea  mov     r8d, [r13+rax*8+8]
0x14000c8ef  sub     r8d, ecx
0x14000c8f2  shl     r8d, 2; Length
0x14000c8f6  mov     [rsp+68h+arg_20], r8d
0x14000c8fe  lea     ecx, ds:0[rcx*4]
0x14000c905  mov     esi, edx
0x14000c907  imul    esi, r12d
0x14000c90b  add     rsi, rcx
0x14000c90e  add     rsi, r11
0x14000c911  mov     [rsp+68h+var_40], rsi
0x14000c916  imul    edx, r15d
0x14000c91a  movsxd  r14, edx
0x14000c91d  add     r14, rcx
0x14000c920  add     r14, r10
0x14000c923  mov     [rsp+68h+var_38], r14
0x14000c928  xor     edi, edi
0x14000c92a  mov     [rsp+68h+var_48], edi
0x14000c92e  cmp     edi, r9d
0x14000c931  jnb     short loc_14000C969
0x14000c933  mov     rdx, r14; Source
0x14000c936  mov     rcx, rsi; Destination
0x14000c939  call    cs:__imp_RtlCopyMemoryNonTemporal
0x14000c940  nop     dword ptr [rax+rax+00h]
0x14000c945  add     rsi, r12
0x14000c948  mov     [rsp+68h+var_40], rsi
0x14000c94d  add     r14, r15
0x14000c950  mov     [rsp+68h+var_38], r14
0x14000c955  inc     edi
0x14000c957  mov     r8d, [rsp+68h+arg_20]
0x14000c95f  mov     r9d, [rsp+68h+arg_30]
0x14000c967  jmp     short loc_14000C92A
0x14000c969  inc     ebx
0x14000c96b  mov     r10, [rsp+68h+arg_10]
0x14000c973  mov     r11, [rsp+68h+arg_0]
0x14000c978  mov     [rsp+68h+var_44], ebx
0x14000c97c  cmp     ebx, 1
0x14000c97f  jb      loc_14000C8CB
0x14000c985  jmp     short loc_14000C9D5
0x14000c987  mov     ecx, 3
0x14000c98c  call    cs:__imp_WdLogSingleEntry0
0x14000c993  nop     dword ptr [rax+rax+00h]
0x14000c998  mov     cs:WdLogGlobalForLineNumber, 0C3Bh
0x14000c9a2  call    cs:__imp_WdLogNewEntry5_WdWarning
0x14000c9a9  nop     dword ptr [rax+rax+00h]
0x14000c9ae  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000c9b5  mov     [rax+18h], rcx
0x14000c9b9  mov     ecx, cs:dword_14003E570
0x14000c9bf  mov     [rax+20h], rcx
0x14000c9c3  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000c9cb  mov     cs:WdLogGlobalForLineNumber, 0C3Bh
0x14000c9d5  lea     r11, [rsp+68h+var_28]
0x14000c9da  mov     rbx, [r11+38h]
0x14000c9de  mov     rsi, [r11+48h]
0x14000c9e2  mov     rsp, r11
0x14000c9e5  pop     r15
0x14000c9e7  pop     r14
0x14000c9e9  pop     r13
0x14000c9eb  pop     r12
0x14000c9ed  pop     rdi
0x14000c9ee  retn
```
