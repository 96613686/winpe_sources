# GetVolumeMountPoint(ushort const *,ushort *,ulong)

- ea: `0x1800effc4`
- end: `0x1800f0303`
- name: `?GetVolumeMountPoint@@YAJPEBGPEAGK@Z`
- size: `831`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x1800f0fa8`

## callees

- `0x1800050c0`
- `0x1800090c0`
- `0x180023800`
- `0x180046e44`
- `0x18004fddc`
- `0x1800effc4`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f02cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f02cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f0070`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f02bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f0070`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f02bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f0087`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f0087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f004f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f004f`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800f003b`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800f003b`

## pseudocode

```c
__int64 __fastcall GetVolumeMountPoint(LPCWSTR lpszVolumeName, unsigned __int16 *a2)
{
  ULONG v3; // r12d
  WCHAR *v4; // rsi
  DWORD v5; // ebx
  unsigned int i; // edi
  SIZE_T v7; // rbx
  HANDLE v8; // rax
  int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int KnownLastErrorHR; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned __int64 v17; // r15
  unsigned __int64 v18; // r13
  unsigned __int64 j; // r14
  unsigned int v20; // eax
  ULONGLONG v21; // rbp
  unsigned int v22; // eax
  __int64 v23; // r10
  unsigned __int64 v24; // r8
  HANDLE ProcessHeap; // rax
  ULONG pulResult; // [rsp+20h] [rbp-68h] BYREF
  ULONGLONG ullOperand; // [rsp+28h] [rbp-60h] BYREF
  unsigned __int16 *v29; // [rsp+30h] [rbp-58h]
  DWORD cchReturnLength; // [rsp+38h] [rbp-50h] BYREF

  v29 = a2;
  ullOperand = 0;
  v3 = 260;
  cchReturnLength = 0;
  pulResult = 260;
  v4 = 0;
  v5 = 0;
  memset_0(a2, 0, 0x208u);
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      if ( i == 3 )
      {
        v16 = 2147549183LL;
        v9 = -2147418113;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_48;
        v15 = 52;
LABEL_47:
        WPP_SF_d(v14[2], v15, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v16);
        goto LABEL_48;
      }
LABEL_24:
      v17 = 0;
      v18 = v5;
      for ( j = 0; j < v18; j += v21 )
      {
        v20 = StringCchLengthW(&v4[j], v18 - j, &ullOperand);
        v9 = v20;
        if ( v20 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v20);
          if ( v9 < 0 )
            goto LABEL_48;
        }
        v21 = ullOperand;
        if ( !ullOperand )
          break;
        if ( ullOperand < v3 )
        {
          v22 = ULongLongToULong(ullOperand, &pulResult);
          v9 = v22;
          if ( v22 )
          {
            if ( (PVOID *)v23 != &WPP_GLOBAL_Control && (*(_BYTE *)(v23 + 28) & 0x40) != 0 )
              WPP_SF_d(*(_QWORD *)(v23 + 16), 54, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v22);
            if ( v9 < 0 )
              goto LABEL_48;
          }
          v3 = pulResult;
          v17 = j;
        }
      }
      v24 = v17 + v3;
      if ( v4[v24 - 1] == 92 )
        v4[v24 - 1] = 0;
      KnownLastErrorHR = StringCchCopyW(v29, 0x104u, &v4[v17]);
      v9 = KnownLastErrorHR;
      if ( !KnownLastErrorHR )
        goto LABEL_48;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_48;
      v15 = 55;
LABEL_46:
      v16 = KnownLastErrorHR;
      goto LABEL_47;
    }
    if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v4, v5, &cchReturnLength) )
      break;
    if ( GetLastError() != 234 )
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      v9 = KnownLastErrorHR;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v15 = 50;
        goto LABEL_46;
      }
LABEL_48:
      if ( v4 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v4);
      }
      return (unsigned int)v9;
    }
    if ( cchReturnLength <= 1 )
    {
      v9 = 0;
      goto LABEL_48;
    }
    v7 = 2LL * cchReturnLength;
    v8 = GetProcessHeap();
    v4 = (WCHAR *)HeapAlloc(v8, 8u, v7);
    if ( !v4 )
    {
      v9 = -2147024882;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v11 = 51;
        v12 = 2147942414LL;
LABEL_19:
        WPP_SF_d(v10[2], v11, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v12);
        return (unsigned int)v9;
      }
      return (unsigned int)v9;
    }
    v5 = cchReturnLength;
  }
  if ( v4 )
    goto LABEL_24;
  v12 = 2147549183LL;
  v9 = -2147418113;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v11 = 49;
    goto LABEL_19;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800effc4  mov     [rsp+arg_10], rbx
0x1800effc9  push    rbp
0x1800effca  push    rsi
0x1800effcb  push    rdi
0x1800effcc  push    r12
0x1800effce  push    r13
0x1800effd0  push    r14
0x1800effd2  push    r15
0x1800effd4  sub     rsp, 50h
0x1800effd8  mov     rax, cs:__security_cookie
0x1800effdf  xor     rax, rsp
0x1800effe2  mov     [rsp+88h+var_48], rax
0x1800effe7  mov     rax, rdx
0x1800effea  mov     [rsp+88h+var_58], rdx
0x1800effef  mov     rbp, rcx
0x1800efff2  mov     [rsp+88h+ullOperand], 0
0x1800efffb  mov     r12d, 104h
0x1800f0001  mov     [rsp+88h+cchReturnLength], 0
0x1800f0009  mov     rcx, rax; void *
0x1800f000c  mov     [rsp+88h+pulResult], r12d
0x1800f0011  xor     edx, edx; Val
0x1800f0013  mov     r8d, 208h; Size
0x1800f0019  xor     esi, esi
0x1800f001b  xor     ebx, ebx
0x1800f001d  call    memset_0
0x1800f0022  xor     edi, edi
0x1800f0024  cmp     edi, 3
0x1800f0027  jnb     loc_1800F0153
0x1800f002d  lea     r9, [rsp+88h+cchReturnLength]; lpcchReturnLength
0x1800f0032  mov     r8d, ebx; cchBufferLength
0x1800f0035  mov     rdx, rsi; lpszVolumePathNames
0x1800f0038  mov     rcx, rbp; lpszVolumeName
0x1800f003b  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1800f0042  nop     dword ptr [rax+rax+00h]
0x1800f0047  test    eax, eax
0x1800f0049  jnz     loc_1800F010C
0x1800f004f  call    cs:__imp_GetLastError
0x1800f0056  nop     dword ptr [rax+rax+00h]
0x1800f005b  cmp     eax, 0EAh
0x1800f0060  jnz     short loc_1800F00DA
0x1800f0062  cmp     [rsp+88h+cchReturnLength], 1
0x1800f0067  jbe     short loc_1800F00D3
0x1800f0069  mov     ebx, [rsp+88h+cchReturnLength]
0x1800f006d  add     rbx, rbx
0x1800f0070  call    cs:__imp_GetProcessHeap
0x1800f0077  nop     dword ptr [rax+rax+00h]
0x1800f007c  mov     r8, rbx; dwBytes
0x1800f007f  mov     edx, 8; dwFlags
0x1800f0084  mov     rcx, rax; hHeap
0x1800f0087  call    cs:__imp_HeapAlloc
0x1800f008e  nop     dword ptr [rax+rax+00h]
0x1800f0093  mov     rsi, rax
0x1800f0096  test    rax, rax
0x1800f0099  jz      short loc_1800F00A3
0x1800f009b  mov     ebx, [rsp+88h+cchReturnLength]
0x1800f009f  inc     edi
0x1800f00a1  jmp     short loc_1800F0024
0x1800f00a3  mov     ebx, 8007000Eh
0x1800f00a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f00af  lea     rdi, WPP_GLOBAL_Control
0x1800f00b6  cmp     rcx, rdi
0x1800f00b9  jz      loc_1800F02DB
0x1800f00bf  test    byte ptr [rcx+1Ch], 40h
0x1800f00c3  jz      loc_1800F02DB
0x1800f00c9  mov     edx, 33h ; '3'
0x1800f00ce  mov     r9d, ebx
0x1800f00d1  jmp     short loc_1800F013E
0x1800f00d3  xor     ebx, ebx
0x1800f00d5  jmp     loc_1800F02B6
0x1800f00da  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800f00df  mov     ebx, eax
0x1800f00e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f00e8  lea     rdi, WPP_GLOBAL_Control
0x1800f00ef  cmp     rcx, rdi
0x1800f00f2  jz      loc_1800F02B6
0x1800f00f8  test    byte ptr [rcx+1Ch], 40h
0x1800f00fc  jz      loc_1800F02B6
0x1800f0102  mov     edx, 32h ; '2'
0x1800f0107  jmp     loc_1800F02A3
0x1800f010c  test    rsi, rsi
0x1800f010f  jnz     short loc_1800F0189
0x1800f0111  mov     r9d, 8000FFFFh
0x1800f0117  mov     ebx, r9d
0x1800f011a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0121  lea     rdi, WPP_GLOBAL_Control
0x1800f0128  cmp     rcx, rdi
0x1800f012b  jz      loc_1800F02DB
0x1800f0131  test    byte ptr [rcx+1Ch], 40h
0x1800f0135  jz      loc_1800F02DB
0x1800f013b  lea     edx, [rsi+31h]
0x1800f013e  mov     rcx, [rcx+10h]
0x1800f0142  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x1800f0149  call    WPP_SF_d
0x1800f014e  jmp     loc_1800F02DB
0x1800f0153  jnz     short loc_1800F0189
0x1800f0155  mov     r9d, 8000FFFFh
0x1800f015b  mov     ebx, r9d
0x1800f015e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0165  lea     rdi, WPP_GLOBAL_Control
0x1800f016c  cmp     rcx, rdi
0x1800f016f  jz      loc_1800F02B6
0x1800f0175  test    byte ptr [rcx+1Ch], 40h
0x1800f0179  jz      loc_1800F02B6
0x1800f017f  mov     edx, 34h ; '4'
0x1800f0184  jmp     loc_1800F02A6
0x1800f0189  xor     r15d, r15d
0x1800f018c  mov     r13d, ebx
0x1800f018f  xor     r14d, r14d
0x1800f0192  lea     rdi, WPP_GLOBAL_Control
0x1800f0199  cmp     r14, r13
0x1800f019c  jnb     loc_1800F025C
0x1800f01a2  mov     rdx, r13
0x1800f01a5  lea     rcx, [rsi+r14*2]; unsigned __int16 *
0x1800f01a9  sub     rdx, r14; unsigned __int64
0x1800f01ac  lea     r8, [rsp+88h+ullOperand]; unsigned __int64 *
0x1800f01b1  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800f01b6  mov     ebx, eax
0x1800f01b8  test    eax, eax
0x1800f01ba  jz      short loc_1800F01F8
0x1800f01bc  mov     r10, cs:WPP_GLOBAL_Control
0x1800f01c3  cmp     r10, rdi
0x1800f01c6  jz      short loc_1800F01EE
0x1800f01c8  test    byte ptr [r10+1Ch], 40h
0x1800f01cd  jz      short loc_1800F01EE
0x1800f01cf  mov     rcx, [r10+10h]
0x1800f01d3  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x1800f01da  mov     edx, 35h ; '5'
0x1800f01df  mov     r9d, eax
0x1800f01e2  call    WPP_SF_d
0x1800f01e7  mov     r10, cs:WPP_GLOBAL_Control
0x1800f01ee  test    ebx, ebx
0x1800f01f0  js      loc_1800F02B6
0x1800f01f6  jmp     short loc_1800F01FF
0x1800f01f8  mov     r10, cs:WPP_GLOBAL_Control
0x1800f01ff  mov     rbp, [rsp+88h+ullOperand]
0x1800f0204  test    rbp, rbp
0x1800f0207  jz      short loc_1800F025C
0x1800f0209  mov     eax, r12d
0x1800f020c  cmp     rbp, rax
0x1800f020f  jnb     short loc_1800F0254
0x1800f0211  lea     rdx, [rsp+88h+pulResult]; pulResult
0x1800f0216  mov     rcx, rbp; ullOperand
0x1800f0219  call    ULongLongToULong
0x1800f021e  mov     ebx, eax
0x1800f0220  test    eax, eax
0x1800f0222  jz      short loc_1800F024C
0x1800f0224  cmp     r10, rdi
0x1800f0227  jz      short loc_1800F0248
0x1800f0229  test    byte ptr [r10+1Ch], 40h
0x1800f022e  jz      short loc_1800F0248
0x1800f0230  mov     rcx, [r10+10h]
0x1800f0234  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x1800f023b  mov     edx, 36h ; '6'
0x1800f0240  mov     r9d, eax
0x1800f0243  call    WPP_SF_d
0x1800f0248  test    ebx, ebx
0x1800f024a  js      short loc_1800F02B6
0x1800f024c  mov     r12d, [rsp+88h+pulResult]
0x1800f0251  mov     r15, r14
0x1800f0254  add     r14, rbp
0x1800f0257  jmp     loc_1800F0199
0x1800f025c  mov     r8d, r12d
0x1800f025f  add     r8, r15
0x1800f0262  cmp     word ptr [rsi+r8*2-2], 5Ch ; '\'
0x1800f0269  jnz     short loc_1800F0273
0x1800f026b  xor     eax, eax
0x1800f026d  mov     [rsi+r8*2-2], ax
0x1800f0273  mov     rcx, [rsp+88h+var_58]; unsigned __int16 *
0x1800f0278  lea     r8, [rsi+r15*2]; unsigned __int16 *
0x1800f027c  mov     edx, 104h; unsigned __int64
0x1800f0281  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f0286  mov     ebx, eax
0x1800f0288  test    eax, eax
0x1800f028a  jz      short loc_1800F02B6
0x1800f028c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0293  cmp     rcx, rdi
0x1800f0296  jz      short loc_1800F02B6
0x1800f0298  test    byte ptr [rcx+1Ch], 40h
0x1800f029c  jz      short loc_1800F02B6
0x1800f029e  mov     edx, 37h ; '7'
0x1800f02a3  mov     r9d, eax
0x1800f02a6  mov     rcx, [rcx+10h]
0x1800f02aa  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x1800f02b1  call    WPP_SF_d
0x1800f02b6  test    rsi, rsi
0x1800f02b9  jz      short loc_1800F02DB
0x1800f02bb  call    cs:__imp_GetProcessHeap
0x1800f02c2  nop     dword ptr [rax+rax+00h]
0x1800f02c7  mov     r8, rsi; lpMem
0x1800f02ca  xor     edx, edx; dwFlags
0x1800f02cc  mov     rcx, rax; hHeap
0x1800f02cf  call    cs:__imp_HeapFree
0x1800f02d6  nop     dword ptr [rax+rax+00h]
0x1800f02db  mov     eax, ebx
0x1800f02dd  mov     rcx, [rsp+88h+var_48]
0x1800f02e2  xor     rcx, rsp; StackCookie
0x1800f02e5  call    __security_check_cookie
0x1800f02ea  mov     rbx, [rsp+88h+arg_10]
0x1800f02f2  add     rsp, 50h
0x1800f02f6  pop     r15
0x1800f02f8  pop     r14
0x1800f02fa  pop     r13
0x1800f02fc  pop     r12
0x1800f02fe  pop     rdi
0x1800f02ff  pop     rsi
0x1800f0300  pop     rbp
0x1800f0301  retn
```
