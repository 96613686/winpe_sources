# FindDiscoveryServiceEx

- ea: `0x180019b38`
- end: `0x180019eb7`
- name: `FindDiscoveryServiceEx`
- size: `895`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800149e0`

## callees

- `0x1800141b0`
- `0x180019734`
- `0x180019b38`
- `0x18001d5ac`
- `0x18001d684`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180019bb2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180019bb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019cf5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019cf5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ce1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ce1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e7c`
- `DMCmnUtils!BigStrcat` at `0x180019bdc`
- `DMCmnUtils!BigStrcat` at `0x180019bdc`

## string_xrefs

- `0x180019b5d`: `FindDiscoveryServiceEx`

## pseudocode

```c
__int64 __fastcall FindDiscoveryServiceEx(const wchar_t *a1, __int64 a2, unsigned __int16 **a3, _DWORD *a4)
{
  unsigned __int16 *v4; // r12
  void *v5; // rsi
  unsigned __int16 *v6; // rbx
  wchar_t *v9; // rax
  unsigned __int16 *v10; // rdi
  unsigned __int16 *v11; // rax
  signed int v12; // edi
  signed int v13; // eax
  int v14; // eax
  unsigned __int16 *v15; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v17; // rax
  unsigned __int16 *v18; // rax
  HANDLE v19; // rax
  HANDLE v20; // rax
  unsigned __int16 *v21; // rbx
  HANDLE v22; // rax
  HANDLE v23; // rax
  unsigned int v25; // [rsp+34h] [rbp-2Ch] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-28h]
  unsigned __int16 *v27; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v28; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v29[2]; // [rsp+50h] [rbp-10h] BYREF
  int v30; // [rsp+A8h] [rbp+48h] BYREF
  int v31; // [rsp+B0h] [rbp+50h]

  v4 = 0;
  v30 = 0;
  v27 = 0;
  v5 = 0;
  v29[0] = "FindDiscoveryServiceEx";
  v6 = 0;
  v28 = 0;
  v25 = 0;
  v29[1] = &v30;
  v31 = 0;
  lpMem = 0;
  if ( !a3 || !a1 || !a4 || (*a4 = 0, *a3 = 0, (v9 = wcschr(a1, 0x40u)) == 0) )
  {
    v12 = -2147024809;
    goto LABEL_37;
  }
  v10 = BigStrcat(3u, L"EnterpriseEnrollment", L".", v9 + 1);
  v11 = LocalAllocToHeapAlloc(v10);
  v6 = v11;
  if ( v10 )
  {
    v13 = SendEmptyDiscoveryRequest(v11);
    v12 = v31;
    v30 = v13;
    if ( v13 >= 0 )
    {
      if ( v31 == 200 )
        goto LABEL_31;
      if ( v31 > 0 )
      {
        v13 = (unsigned __int16)v31 | 0x80190000;
        v30 = v13;
      }
      else
      {
        v30 = v31;
        v13 = v31;
      }
      if ( v13 >= 0 )
        goto LABEL_31;
    }
    v5 = lpMem;
    if ( !lpMem )
    {
      v14 = SendEmptyDiscoveryRequest(v6);
      v5 = 0;
      v30 = v14;
      if ( v14 < 0 )
      {
        v12 = v14;
        goto LABEL_38;
      }
      if ( v12 )
      {
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80190000;
      }
      else
      {
        v12 = -2147023728;
      }
      goto LABEL_37;
    }
    v30 = ParseServiceURL((wchar_t *)lpMem, &v25, &v27, &v28, 0);
    v12 = v30;
    if ( v30 < 0 )
    {
      v4 = v27;
      goto LABEL_38;
    }
    v15 = v27;
    if ( v6 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
    }
    *a4 = 1;
    lpMem = 0;
    v6 = v15;
    if ( v5 )
    {
      v17 = GetProcessHeap();
      HeapFree(v17, 0, v5);
    }
    v13 = SendEmptyDiscoveryRequest(v15);
    v30 = v13;
    if ( v13 < 0 )
    {
      v12 = v13;
      goto LABEL_33;
    }
    v12 = v31;
    if ( v31 == 200 )
    {
LABEL_31:
      v12 = v13;
    }
    else
    {
      if ( v31 > 0 )
        v12 = (unsigned __int16)v31 | 0x80190000;
      v30 = v12;
      if ( v12 < 0 )
        goto LABEL_33;
    }
    v18 = v6;
    v6 = 0;
    *a3 = v18;
LABEL_33:
    v5 = lpMem;
    goto LABEL_38;
  }
  v12 = -2147024882;
LABEL_37:
  v30 = v12;
LABEL_38:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v29);
  if ( v5 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  if ( v6 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v6);
  }
  v21 = v28;
  if ( v28 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
  }
  if ( v4 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v4);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180019b38  mov     [rsp-38h+arg_0], rbx
0x180019b3d  mov     [rsp-38h+arg_8], edx
0x180019b41  push    rbp
0x180019b42  push    rsi
0x180019b43  push    rdi
0x180019b44  push    r12
0x180019b46  push    r13
0x180019b48  push    r14
0x180019b4a  push    r15
0x180019b4c  mov     rbp, rsp
0x180019b4f  sub     rsp, 60h
0x180019b53  xor     r12d, r12d
0x180019b56  mov     [rbp+arg_8], 0
0x180019b5d  lea     rax, aFinddiscoverys_0; "FindDiscoveryServiceEx"
0x180019b64  mov     [rbp+var_20], r12
0x180019b68  xor     esi, esi
0x180019b6a  mov     [rbp+var_10], rax
0x180019b6e  xor     ebx, ebx
0x180019b70  mov     [rbp+var_18], r12
0x180019b74  mov     [rbp+var_2C], r12d
0x180019b78  lea     rax, [rbp+arg_8]
0x180019b7c  mov     [rbp+var_8], rax
0x180019b80  mov     r15, r9
0x180019b83  mov     [rbp+arg_10], r12d
0x180019b87  mov     r13, r8
0x180019b8a  mov     [rbp+lpMem], rsi
0x180019b8e  test    r8, r8
0x180019b91  jz      loc_180019DF3
0x180019b97  test    rcx, rcx
0x180019b9a  jz      loc_180019DF3
0x180019ba0  test    r9, r9
0x180019ba3  jz      loc_180019DF3
0x180019ba9  mov     [r9], ebx
0x180019bac  lea     edx, [rbx+40h]; Ch
0x180019baf  mov     [r8], rbx
0x180019bb2  call    cs:__imp_wcschr
0x180019bb9  nop     dword ptr [rax+rax+00h]
0x180019bbe  test    rax, rax
0x180019bc1  jz      loc_180019DF3
0x180019bc7  lea     r9, [rax+2]
0x180019bcb  lea     r8, asc_180051370; "."
0x180019bd2  lea     rdx, aEnterpriseenro; "EnterpriseEnrollment"
0x180019bd9  lea     ecx, [rbx+3]
0x180019bdc  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x180019be3  nop     dword ptr [rax+rax+00h]
0x180019be8  mov     rcx, rax; hMem
0x180019beb  mov     rdi, rax
0x180019bee  call    ?LocalAllocToHeapAlloc@@YAPEAGPEAG@Z; LocalAllocToHeapAlloc(ushort *)
0x180019bf3  mov     rbx, rax
0x180019bf6  test    rdi, rdi
0x180019bf9  jnz     short loc_180019C05
0x180019bfb  mov     edi, 8007000Eh
0x180019c00  jmp     loc_180019DF8
0x180019c05  lea     r9, [rbp+lpMem]
0x180019c09  mov     dl, 1
0x180019c0b  lea     r8, [rbp+arg_10]
0x180019c0f  mov     rcx, rbx; unsigned __int16 *
0x180019c12  call    SendEmptyDiscoveryRequest
0x180019c17  mov     edi, [rbp+arg_10]
0x180019c1a  mov     [rbp+arg_8], eax
0x180019c1d  test    eax, eax
0x180019c1f  js      short loc_180019C4B
0x180019c21  cmp     edi, 0C8h
0x180019c27  jz      loc_180019DD8
0x180019c2d  test    edi, edi
0x180019c2f  jg      short loc_180019C38
0x180019c31  mov     [rbp+arg_8], edi
0x180019c34  mov     eax, edi
0x180019c36  jmp     short loc_180019C43
0x180019c38  movzx   eax, di
0x180019c3b  or      eax, 80190000h
0x180019c40  mov     [rbp+arg_8], eax
0x180019c43  test    eax, eax
0x180019c45  jns     loc_180019DD8
0x180019c4b  mov     rsi, [rbp+lpMem]
0x180019c4f  xor     r14b, r14b
0x180019c52  test    rsi, rsi
0x180019c55  jnz     short loc_180019CB2
0x180019c57  lea     r9, [rbp+lpMem]
0x180019c5b  mov     [rbp+var_30], r12d
0x180019c5f  lea     r8, [rbp+var_30]
0x180019c63  xor     edx, edx
0x180019c65  mov     rcx, rbx; unsigned __int16 *
0x180019c68  call    SendEmptyDiscoveryRequest
0x180019c6d  mov     rsi, [rbp+lpMem]
0x180019c71  mov     [rbp+arg_8], eax
0x180019c74  test    eax, eax
0x180019c76  js      short loc_180019CAB
0x180019c78  cmp     [rbp+var_30], 12Eh
0x180019c7f  jnz     short loc_180019C89
0x180019c81  mov     r14b, 1
0x180019c84  test    rsi, rsi
0x180019c87  jnz     short loc_180019CB2
0x180019c89  test    edi, edi
0x180019c8b  jz      short loc_180019CA1
0x180019c8d  jle     loc_180019DF8
0x180019c93  movzx   edi, di
0x180019c96  or      edi, 80190000h
0x180019c9c  jmp     loc_180019DF8
0x180019ca1  mov     edi, 80070490h
0x180019ca6  jmp     loc_180019DF8
0x180019cab  mov     edi, eax
0x180019cad  jmp     loc_180019DFB
0x180019cb2  lea     r9, [rbp+var_18]; unsigned __int16 **
0x180019cb6  mov     [rsp+60h+var_40], r12d; int
0x180019cbb  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180019cbf  mov     rcx, rsi; unsigned __int16 *
0x180019cc2  lea     rdx, [rbp+var_2C]; unsigned int *
0x180019cc6  call    ?ParseServiceURL@@YAJPEBGPEAKPEAPEAG2H@Z; ParseServiceURL(ushort const *,ulong *,ushort * *,ushort * *,int)
0x180019ccb  mov     [rbp+arg_8], eax
0x180019cce  mov     edi, eax
0x180019cd0  test    eax, eax
0x180019cd2  js      loc_180019DED
0x180019cd8  mov     rdi, [rbp+var_20]
0x180019cdc  test    rbx, rbx
0x180019cdf  jz      short loc_180019D01
0x180019ce1  call    cs:__imp_GetProcessHeap
0x180019ce8  nop     dword ptr [rax+rax+00h]
0x180019ced  mov     r8, rbx; lpMem
0x180019cf0  xor     edx, edx; dwFlags
0x180019cf2  mov     rcx, rax; hHeap
0x180019cf5  call    cs:__imp_HeapFree
0x180019cfc  nop     dword ptr [rax+rax+00h]
0x180019d01  mov     dword ptr [r15], 1
0x180019d08  test    r14b, r14b
0x180019d0b  jz      short loc_180019D72
0x180019d0d  lea     rcx, [rbp+var_10]; this
0x180019d11  mov     [r13+0], rdi
0x180019d15  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180019d1a  test    rsi, rsi
0x180019d1d  jz      short loc_180019D3F
0x180019d1f  call    cs:__imp_GetProcessHeap
0x180019d26  nop     dword ptr [rax+rax+00h]
0x180019d2b  mov     r8, rsi; lpMem
0x180019d2e  xor     edx, edx; dwFlags
0x180019d30  mov     rcx, rax; hHeap
0x180019d33  call    cs:__imp_HeapFree
0x180019d3a  nop     dword ptr [rax+rax+00h]
0x180019d3f  mov     rbx, [rbp+var_18]
0x180019d43  test    rbx, rbx
0x180019d46  jz      short loc_180019D68
0x180019d48  call    cs:__imp_GetProcessHeap
0x180019d4f  nop     dword ptr [rax+rax+00h]
0x180019d54  mov     r8, rbx; lpMem
0x180019d57  xor     edx, edx; dwFlags
0x180019d59  mov     rcx, rax; hHeap
0x180019d5c  call    cs:__imp_HeapFree
0x180019d63  nop     dword ptr [rax+rax+00h]
0x180019d68  mov     eax, 8018001Ah
0x180019d6d  jmp     loc_180019E9E
0x180019d72  mov     [rbp+lpMem], r12
0x180019d76  mov     rbx, rdi
0x180019d79  test    rsi, rsi
0x180019d7c  jz      short loc_180019D9E
0x180019d7e  call    cs:__imp_GetProcessHeap
0x180019d85  nop     dword ptr [rax+rax+00h]
0x180019d8a  mov     r8, rsi; lpMem
0x180019d8d  xor     edx, edx; dwFlags
0x180019d8f  mov     rcx, rax; hHeap
0x180019d92  call    cs:__imp_HeapFree
0x180019d99  nop     dword ptr [rax+rax+00h]
0x180019d9e  lea     r9, [rbp+lpMem]
0x180019da2  mov     dl, 1
0x180019da4  lea     r8, [rbp+arg_10]
0x180019da8  mov     rcx, rdi; unsigned __int16 *
0x180019dab  call    SendEmptyDiscoveryRequest
0x180019db0  mov     [rbp+arg_8], eax
0x180019db3  test    eax, eax
0x180019db5  js      short loc_180019DE9
0x180019db7  mov     edi, [rbp+arg_10]
0x180019dba  cmp     edi, 0C8h
0x180019dc0  jz      short loc_180019DD8
0x180019dc2  test    edi, edi
0x180019dc4  jle     short loc_180019DCF
0x180019dc6  movzx   edi, di
0x180019dc9  or      edi, 80190000h
0x180019dcf  mov     [rbp+arg_8], edi
0x180019dd2  test    edi, edi
0x180019dd4  jns     short loc_180019DDA
0x180019dd6  jmp     short loc_180019DE3
0x180019dd8  mov     edi, eax
0x180019dda  mov     rax, rbx
0x180019ddd  xor     ebx, ebx
0x180019ddf  mov     [r13+0], rax
0x180019de3  mov     rsi, [rbp+lpMem]
0x180019de7  jmp     short loc_180019DFB
0x180019de9  mov     edi, eax
0x180019deb  jmp     short loc_180019DE3
0x180019ded  mov     r12, [rbp+var_20]
0x180019df1  jmp     short loc_180019DFB
0x180019df3  mov     edi, 80070057h
0x180019df8  mov     [rbp+arg_8], edi
0x180019dfb  lea     rcx, [rbp+var_10]; this
0x180019dff  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180019e04  test    rsi, rsi
0x180019e07  jz      short loc_180019E29
0x180019e09  call    cs:__imp_GetProcessHeap
0x180019e10  nop     dword ptr [rax+rax+00h]
0x180019e15  mov     r8, rsi; lpMem
0x180019e18  xor     edx, edx; dwFlags
0x180019e1a  mov     rcx, rax; hHeap
0x180019e1d  call    cs:__imp_HeapFree
0x180019e24  nop     dword ptr [rax+rax+00h]
0x180019e29  test    rbx, rbx
0x180019e2c  jz      short loc_180019E4E
0x180019e2e  call    cs:__imp_GetProcessHeap
0x180019e35  nop     dword ptr [rax+rax+00h]
0x180019e3a  mov     r8, rbx; lpMem
0x180019e3d  xor     edx, edx; dwFlags
0x180019e3f  mov     rcx, rax; hHeap
0x180019e42  call    cs:__imp_HeapFree
0x180019e49  nop     dword ptr [rax+rax+00h]
0x180019e4e  mov     rbx, [rbp+var_18]
0x180019e52  test    rbx, rbx
0x180019e55  jz      short loc_180019E77
0x180019e57  call    cs:__imp_GetProcessHeap
0x180019e5e  nop     dword ptr [rax+rax+00h]
0x180019e63  mov     r8, rbx; lpMem
0x180019e66  xor     edx, edx; dwFlags
0x180019e68  mov     rcx, rax; hHeap
0x180019e6b  call    cs:__imp_HeapFree
0x180019e72  nop     dword ptr [rax+rax+00h]
0x180019e77  test    r12, r12
0x180019e7a  jz      short loc_180019E9C
0x180019e7c  call    cs:__imp_GetProcessHeap
0x180019e83  nop     dword ptr [rax+rax+00h]
0x180019e88  mov     r8, r12; lpMem
0x180019e8b  xor     edx, edx; dwFlags
0x180019e8d  mov     rcx, rax; hHeap
0x180019e90  call    cs:__imp_HeapFree
0x180019e97  nop     dword ptr [rax+rax+00h]
0x180019e9c  mov     eax, edi
0x180019e9e  mov     rbx, [rsp+60h+arg_0]
0x180019ea6  add     rsp, 60h
0x180019eaa  pop     r15
0x180019eac  pop     r14
0x180019eae  pop     r13
0x180019eb0  pop     r12
0x180019eb2  pop     rdi
0x180019eb3  pop     rsi
0x180019eb4  pop     rbp
0x180019eb5  retn
```
