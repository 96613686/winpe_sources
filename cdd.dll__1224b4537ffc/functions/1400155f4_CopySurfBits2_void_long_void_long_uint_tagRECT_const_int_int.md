# CopySurfBits2(void *,long,void *,long,uint,tagRECT const *,int,int)

- ea: `0x1400155f4`
- end: `0x14001575d`
- name: `?CopySurfBits2@@YAXPEAXJ0JIPEBUtagRECT@@HH@Z`
- size: `361`
- prototype: `void __fastcall(char *, int, char *, int, unsigned int, const struct tagRECT *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400155a0`

## callees

- `0x1400155f4`

## import_xrefs

- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x1400156b9`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x1400156b9`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14001570f`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14001570f`
- `watchdog!WdLogSingleEntry0` at `0x1400156f9`
- `watchdog!WdLogSingleEntry0` at `0x1400156f9`

## pseudocode

```c
void __fastcall CopySurfBits2(
        char *a1,
        int a2,
        char *a3,
        int a4,
        unsigned int a5,
        const struct tagRECT *a6,
        int a7,
        int a8)
{
  __int64 v8; // r15
  char *v9; // r10
  __int64 v10; // r12
  char *v11; // r11
  unsigned int i; // ebx
  LONG left; // r8d
  LONG top; // edx
  unsigned int v15; // r9d
  unsigned int v16; // r13d
  char *v17; // rsi
  char *v18; // r14
  unsigned int j; // edi
  unsigned int v20; // [rsp+24h] [rbp-44h]

  v8 = a4;
  v9 = a3;
  v10 = a2;
  v11 = a1;
  for ( i = 0; i < a5; ++i )
  {
    left = a6[i].left;
    top = a6[i].top;
    v15 = a6[i].bottom - top;
    v20 = v15;
    v16 = 4 * (a6[i].right - left);
    v17 = &v11[(int)v10 * top + 4 * left];
    v18 = &v9[(int)v8 * (top + a8) + 4 * (left + a7)];
    for ( j = 0; j < v15; ++j )
    {
      RtlCopyMemoryNonTemporal(v17, v18, v16);
      v17 += v10;
      v18 += v8;
      v15 = v20;
    }
    v9 = a3;
    v11 = a1;
  }
}

```

## disassembly

```asm
0x1400155f4  mov     rax, rsp
0x1400155f7  mov     [rax+10h], rbx
0x1400155fb  mov     [rax+20h], rsi
0x1400155ff  mov     [rax+18h], r8
0x140015603  mov     [rax+8], rcx
0x140015607  push    rdi
0x140015608  push    r12
0x14001560a  push    r13
0x14001560c  push    r14
0x14001560e  push    r15
0x140015610  sub     rsp, 40h
0x140015614  movsxd  r15, r9d
0x140015617  mov     r10, r8
0x14001561a  movsxd  r12, edx
0x14001561d  mov     r11, rcx
0x140015620  xor     ebx, ebx
0x140015622  mov     [rsp+68h+var_40], ebx
0x140015626  cmp     ebx, [rsp+68h+arg_20]
0x14001562d  jnb     loc_1400156F2
0x140015633  mov     eax, ebx
0x140015635  add     rax, rax
0x140015638  mov     rcx, [rsp+68h+arg_28]
0x140015640  mov     r8d, [rcx+rax*8]
0x140015644  mov     edx, [rcx+rax*8+4]
0x140015648  mov     r9d, [rcx+rax*8+0Ch]
0x14001564d  sub     r9d, edx
0x140015650  mov     [rsp+68h+var_44], r9d
0x140015655  mov     r13d, [rcx+rax*8+8]
0x14001565a  sub     r13d, r8d
0x14001565d  shl     r13d, 2
0x140015661  mov     eax, edx
0x140015663  imul    eax, r12d
0x140015667  cdqe
0x140015669  lea     esi, ds:0[r8*4]
0x140015671  add     rax, r11
0x140015674  add     rsi, rax
0x140015677  mov     [rsp+68h+var_38], rsi
0x14001567c  mov     eax, [rsp+68h+arg_38]
0x140015683  add     eax, edx
0x140015685  imul    eax, r15d
0x140015689  cdqe
0x14001568b  mov     r14d, [rsp+68h+arg_30]
0x140015693  add     r14d, r8d
0x140015696  shl     r14d, 2
0x14001569a  add     rax, r10
0x14001569d  add     r14, rax
0x1400156a0  mov     [rsp+68h+var_30], r14
0x1400156a5  xor     edi, edi
0x1400156a7  mov     [rsp+68h+var_48], edi
0x1400156ab  cmp     edi, r9d
0x1400156ae  jnb     short loc_1400156DE
0x1400156b0  mov     r8d, r13d; Length
0x1400156b3  mov     rdx, r14; Source
0x1400156b6  mov     rcx, rsi; Destination
0x1400156b9  call    cs:__imp_RtlCopyMemoryNonTemporal
0x1400156c0  nop     dword ptr [rax+rax+00h]
0x1400156c5  add     rsi, r12
0x1400156c8  mov     [rsp+68h+var_38], rsi
0x1400156cd  add     r14, r15
0x1400156d0  mov     [rsp+68h+var_30], r14
0x1400156d5  inc     edi
0x1400156d7  mov     r9d, [rsp+68h+var_44]
0x1400156dc  jmp     short loc_1400156A7
0x1400156de  inc     ebx
0x1400156e0  mov     r10, [rsp+68h+arg_10]
0x1400156e8  mov     r11, [rsp+68h+arg_0]
0x1400156ed  jmp     loc_140015622
0x1400156f2  jmp     short loc_140015742
0x1400156f4  mov     ecx, 3
0x1400156f9  call    cs:__imp_WdLogSingleEntry0
0x140015700  nop     dword ptr [rax+rax+00h]
0x140015705  mov     cs:WdLogGlobalForLineNumber, 0C87h
0x14001570f  call    cs:__imp_WdLogNewEntry5_WdWarning
0x140015716  nop     dword ptr [rax+rax+00h]
0x14001571b  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140015722  mov     [rax+18h], rcx
0x140015726  mov     ecx, cs:dword_14003E570
0x14001572c  mov     [rax+20h], rcx
0x140015730  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140015738  mov     cs:WdLogGlobalForLineNumber, 0C87h
0x140015742  lea     r11, [rsp+68h+var_28]
0x140015747  mov     rbx, [r11+38h]
0x14001574b  mov     rsi, [r11+48h]
0x14001574f  mov     rsp, r11
0x140015752  pop     r15
0x140015754  pop     r14
0x140015756  pop     r13
0x140015758  pop     r12
0x14001575a  pop     rdi
0x14001575b  retn
```
