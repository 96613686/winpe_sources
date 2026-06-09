# FwStringCopy

- ea: `0x1800045f0`
- end: `0x180004740`
- name: `FwStringCopy`
- size: `336`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `15`
- callee_count: `6`
- tags: ``

## callers

- `0x180001eb0`
- `0x180002e70`
- `0x1800030b0`
- `0x1800043a0`
- `0x1800053c0`
- `0x18001f3a0`
- `0x18001ff80`
- `0x1800205fc`
- `0x1800207f0`
- `0x180020b10`
- `0x180020c50`
- `0x18002a770`
- `0x18002acb0`
- `0x18002b538`
- `0x18002c0e0`

## callees

- `0x1800045f0`
- `0x180004750`
- `0x1800047e0`
- `0x1800130bc`
- `0x180017b58`
- `0x18002f674`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004731`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004731`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004670`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004670`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000465f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000465f`

## string_xrefs

- `0x1800046da`: `FwStringCopy`
- `0x180004702`: `FwStringCopy`
- `0x18000471c`: `FwStringCopy`

## pseudocode

```c
__int64 __fastcall FwStringCopy(_WORD *Src, _QWORD *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  SIZE_T v7; // rsi
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  unsigned int v10; // ebx
  int v11; // edx
  int v12; // r8d

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids, Src);
  result = 0;
  *a2 = 0;
  if ( Src )
  {
    v5 = -1;
    while ( Src[++v5] != 0 )
      ;
    if ( (unsigned __int64)(v5 + 1) > 0x7FFFFFFFFFFFFFFFLL )
    {
      v10 = -2147024362;
      FwReportReturnError("FwStringCopy", 2147942934LL);
      goto LABEL_14;
    }
    v7 = 2 * (v5 + 1);
    if ( v7 )
    {
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 8u, v7);
      *a2 = v9;
      if ( v9 )
      {
        v10 = 0;
        memcpy_0(v9, Src, v7);
        return v10;
      }
    }
    else
    {
      SetLastError(0x57u);
      *a2 = 0;
    }
    result = FwReportErrorAsWinError("FwStringCopy", "FwAlloc", 8);
    v10 = result;
    if ( (int)result < 0 )
    {
LABEL_14:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, (unsigned int)"FwStringCopy", v10);
      return v10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800045f0  mov     [rsp+arg_8], rbx
0x1800045f5  mov     [rsp+arg_10], rdi
0x1800045fa  push    r14
0x1800045fc  sub     rsp, 30h
0x180004600  mov     rbx, rdx
0x180004603  mov     rdi, rcx
0x180004606  mov     rcx, cs:WPP_GLOBAL_Control
0x18000460d  lea     r14, WPP_GLOBAL_Control
0x180004614  cmp     rcx, r14
0x180004617  jnz     loc_1800046A6
0x18000461d  xor     eax, eax
0x18000461f  mov     [rbx], rax
0x180004622  test    rdi, rdi
0x180004625  jz      short loc_180004695
0x180004627  mov     [rsp+38h+arg_0], rsi
0x18000462c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004633  cmp     word ptr [rdi+rax*2+2], 0
0x180004639  lea     rax, [rax+1]
0x18000463d  jnz     short loc_180004633
0x18000463f  lea     rsi, [rax+1]
0x180004643  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000464d  cmp     rsi, rax
0x180004650  ja      loc_180004717
0x180004656  add     rsi, rsi
0x180004659  jz      loc_18000472C
0x18000465f  call    cs:__imp_GetProcessHeap
0x180004665  mov     r8, rsi; dwBytes
0x180004668  mov     edx, 8; dwFlags
0x18000466d  mov     rcx, rax; hHeap
0x180004670  call    cs:__imp_HeapAlloc
0x180004676  mov     [rbx], rax
0x180004679  test    rax, rax
0x18000467c  jz      short loc_1800046CD
0x18000467e  xor     ebx, ebx
0x180004680  mov     r8, rsi; Size
0x180004683  mov     rdx, rdi; Src
0x180004686  mov     rcx, rax; void *
0x180004689  call    memcpy_0
0x18000468e  mov     eax, ebx
0x180004690  mov     rsi, [rsp+38h+arg_0]
0x180004695  mov     rbx, [rsp+38h+arg_8]
0x18000469a  mov     rdi, [rsp+38h+arg_10]
0x18000469f  add     rsp, 30h
0x1800046a3  pop     r14
0x1800046a5  retn
0x1800046a6  test    byte ptr [rcx+1Ch], 4
0x1800046aa  jz      loc_18000461D
0x1800046b0  mov     rcx, [rcx+10h]
0x1800046b4  lea     r8, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids
0x1800046bb  mov     edx, 0Dh
0x1800046c0  mov     r9, rdi
0x1800046c3  call    WPP_SF_S
0x1800046c8  jmp     loc_18000461D
0x1800046cd  mov     r8d, 8
0x1800046d3  lea     rdx, aFwalloc_0; "FwAlloc"
0x1800046da  lea     rcx, aFwstringcopy_0; "FwStringCopy"
0x1800046e1  call    FwReportErrorAsWinError
0x1800046e6  mov     ebx, eax
0x1800046e8  test    eax, eax
0x1800046ea  jns     short loc_180004690
0x1800046ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046f3  cmp     rcx, r14
0x1800046f6  jz      short loc_18000468E
0x1800046f8  test    byte ptr [rcx+1Ch], 1
0x1800046fc  jz      short loc_18000468E
0x1800046fe  mov     rcx, [rcx+10h]
0x180004702  lea     r9, aFwstringcopy_0; "FwStringCopy"
0x180004709  mov     [rsp+38h+var_18], ebx
0x18000470d  call    WPP_SF_sD
0x180004712  jmp     loc_18000468E
0x180004717  mov     ebx, 80070216h
0x18000471c  lea     rcx, aFwstringcopy_0; "FwStringCopy"
0x180004723  mov     edx, ebx
0x180004725  call    FwReportReturnError
0x18000472a  jmp     short loc_1800046EC
0x18000472c  mov     ecx, 57h ; 'W'; dwErrCode
0x180004731  call    cs:__imp_SetLastError
0x180004737  mov     qword ptr [rbx], 0
0x18000473e  jmp     short loc_1800046CD
```
