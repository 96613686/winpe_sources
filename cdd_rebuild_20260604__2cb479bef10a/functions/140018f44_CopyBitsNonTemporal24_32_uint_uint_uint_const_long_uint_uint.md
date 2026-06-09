# CopyBitsNonTemporal24_32(uint *,uint,uint const *,long,uint,uint)

- ea: `0x140018f44`
- end: `0x1400190bd`
- name: `?CopyBitsNonTemporal24_32@@YAXPEAIIPEBIJII@Z`
- size: `377`
- prototype: `void __fastcall(unsigned int *, unsigned int, const unsigned int *, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a254`

## callees

- `0x140018f44`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdWarning` at `0x140019079`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140019079`
- `watchdog!WdLogSingleEntry0` at `0x140019063`
- `watchdog!WdLogSingleEntry0` at `0x140019063`

## pseudocode

```c
void __fastcall CopyBitsNonTemporal24_32(
        unsigned int *a1,
        unsigned int a2,
        const unsigned int *a3,
        int a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  __int64 v7; // rsi
  unsigned int v9; // edx
  const unsigned int *v10; // r11
  int *v11; // rbx
  unsigned int i; // r9d
  int v13; // ecx
  const unsigned int *v14; // r11
  unsigned int *v15; // rbx
  unsigned int j; // r9d
  int v17; // ecx

  v6 = a4;
  v7 = a2;
  v9 = 0;
  if ( g_SSE2InstructionsAvailable )
  {
    while ( v9 < a5 )
    {
      v10 = a3;
      v11 = (int *)a1;
      for ( i = 0; i < a6; ++i )
      {
        v13 = *(unsigned __int8 *)v10 | (*(unsigned __int16 *)((char *)v10 + 1) << 8);
        v10 = (const unsigned int *)((char *)v10 + 3);
        _mm_stream_si32(v11++, v13);
      }
      a3 = (const unsigned int *)((char *)a3 + v6);
      a1 = (unsigned int *)((char *)a1 + v7);
      ++v9;
    }
  }
  else
  {
    while ( v9 < a5 )
    {
      v14 = a3;
      v15 = a1;
      for ( j = 0; j < a6; ++j )
      {
        v17 = *(unsigned __int8 *)v14 | (*(unsigned __int16 *)((char *)v14 + 1) << 8);
        v14 = (const unsigned int *)((char *)v14 + 3);
        *v15++ = v17;
      }
      a3 = (const unsigned int *)((char *)a3 + v6);
      a1 = (unsigned int *)((char *)a1 + v7);
      ++v9;
    }
  }
}

```

## disassembly

```asm
0x140018f44  mov     [rsp+arg_0], rbx
0x140018f49  mov     [rsp+arg_8], rsi
0x140018f4e  push    rdi
0x140018f4f  sub     rsp, 60h
0x140018f53  movsxd  rdi, r9d
0x140018f56  mov     esi, edx
0x140018f58  mov     r10, rcx
0x140018f5b  mov     [rsp+68h+var_38], r8
0x140018f60  mov     [rsp+68h+var_30], rcx
0x140018f65  xor     edx, edx
0x140018f67  cmp     cs:?g_SSE2InstructionsAvailable@@3HA, edx; int g_SSE2InstructionsAvailable
0x140018f6d  jz      short loc_140018FE8
0x140018f6f  mov     [rsp+68h+var_44], edx
0x140018f73  cmp     edx, [rsp+68h+arg_20]
0x140018f7a  jnb     loc_14001905C
0x140018f80  mov     r11, r8
0x140018f83  mov     [rsp+68h+var_28], r8
0x140018f88  mov     rbx, r10
0x140018f8b  mov     [rsp+68h+var_20], rbx
0x140018f90  xor     r9d, r9d
0x140018f93  mov     [rsp+68h+var_48], r9d
0x140018f98  cmp     r9d, [rsp+68h+arg_28]
0x140018fa0  jnb     short loc_140018FD4
0x140018fa2  movzx   ecx, byte ptr [r11+2]
0x140018fa7  shl     ecx, 8
0x140018faa  movzx   eax, byte ptr [r11+1]
0x140018faf  or      ecx, eax
0x140018fb1  shl     ecx, 8
0x140018fb4  movzx   eax, byte ptr [r11]
0x140018fb8  or      ecx, eax
0x140018fba  add     r11, 3
0x140018fbe  mov     [rsp+68h+var_28], r11
0x140018fc3  movnti  dword ptr [rbx], ecx
0x140018fc6  add     rbx, 4
0x140018fca  mov     [rsp+68h+var_20], rbx
0x140018fcf  inc     r9d
0x140018fd2  jmp     short loc_140018F93
0x140018fd4  add     r8, rdi
0x140018fd7  mov     [rsp+68h+var_38], r8
0x140018fdc  add     r10, rsi
0x140018fdf  mov     [rsp+68h+var_30], r10
0x140018fe4  inc     edx
0x140018fe6  jmp     short loc_140018F6F
0x140018fe8  mov     [rsp+68h+var_3C], edx
0x140018fec  cmp     edx, [rsp+68h+arg_20]
0x140018ff3  jnb     short loc_14001905C
0x140018ff5  mov     r11, r8
0x140018ff8  mov     [rsp+68h+var_18], r8
0x140018ffd  mov     rbx, r10
0x140019000  mov     [rsp+68h+var_10], rbx
0x140019005  xor     r9d, r9d
0x140019008  mov     [rsp+68h+var_40], r9d
0x14001900d  cmp     r9d, [rsp+68h+arg_28]
0x140019015  jnb     short loc_140019048
0x140019017  movzx   ecx, byte ptr [r11+2]
0x14001901c  shl     ecx, 8
0x14001901f  movzx   eax, byte ptr [r11+1]
0x140019024  or      ecx, eax
0x140019026  shl     ecx, 8
0x140019029  movzx   eax, byte ptr [r11]
0x14001902d  or      ecx, eax
0x14001902f  add     r11, 3
0x140019033  mov     [rsp+68h+var_18], r11
0x140019038  mov     [rbx], ecx
0x14001903a  add     rbx, 4
0x14001903e  mov     [rsp+68h+var_10], rbx
0x140019043  inc     r9d
0x140019046  jmp     short loc_140019008
0x140019048  add     r8, rdi
0x14001904b  mov     [rsp+68h+var_38], r8
0x140019050  add     r10, rsi
0x140019053  mov     [rsp+68h+var_30], r10
0x140019058  inc     edx
0x14001905a  jmp     short loc_140018FE8
0x14001905c  jmp     short loc_1400190AC
0x14001905e  mov     ecx, 3
0x140019063  call    cs:__imp_WdLogSingleEntry0
0x14001906a  nop     dword ptr [rax+rax+00h]
0x14001906f  mov     cs:WdLogGlobalForLineNumber, 0B7Bh
0x140019079  call    cs:__imp_WdLogNewEntry5_WdWarning
0x140019080  nop     dword ptr [rax+rax+00h]
0x140019085  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001908c  mov     [rax+18h], rcx
0x140019090  mov     ecx, cs:dword_14003E570
0x140019096  mov     [rax+20h], rcx
0x14001909a  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400190a2  mov     cs:WdLogGlobalForLineNumber, 0B7Bh
0x1400190ac  mov     rbx, [rsp+68h+arg_0]
0x1400190b1  mov     rsi, [rsp+68h+arg_8]
0x1400190b6  add     rsp, 60h
0x1400190ba  pop     rdi
0x1400190bb  retn
```
