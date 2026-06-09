# DisplayExtensions(HWND__ *,ulong,_CERT_EXTENSION *,int,ulong *)

- ea: `0x180011a28`
- end: `0x180011b82`
- name: `?DisplayExtensions@@YAXPEAUHWND__@@KPEAU_CERT_EXTENSION@@HPEAK@Z`
- size: `346`
- prototype: `void __usercall(HWND hWnd@<rcx>, unsigned int@<edx>, struct _CERT_EXTENSION *@<r8>, int@<r9d>, unsigned int *)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180009000`
- `0x180009834`
- `0x18000b220`
- `0x18000e040`

## callees

- `0x18001195c`
- `0x180011a28`
- `0x1800125cc`
- `0x180031c94`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `USER32!SendMessageA` at `0x180011b28`
- `USER32!SendMessageA` at `0x180011b28`

## pseudocode

```c
void __fastcall DisplayExtensions(HWND hWnd, unsigned int a2, struct _CERT_EXTENSION *a3, int a4, unsigned int *a5)
{
  unsigned int v9; // edi
  __int64 v10; // rbx
  __int64 v11; // rax
  DWORD cbData; // r8d
  unsigned __int8 *pbData; // rdx
  const CHAR *pszObjId; // rcx
  int lParam; // [rsp+30h] [rbp-D0h] BYREF
  int lParam_4; // [rsp+34h] [rbp-CCh]
  int v17; // [rsp+38h] [rbp-C8h]
  __int64 v18; // [rsp+3Ch] [rbp-C4h]
  unsigned __int16 *v19; // [rsp+48h] [rbp-B8h]
  int v20; // [rsp+50h] [rbp-B0h]
  _BYTE v21[12]; // [rsp+54h] [rbp-ACh]
  unsigned __int16 v22[768]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(&lParam, 0, 0x58u);
  lParam = 15;
  v18 = 0;
  v19 = v22;
  v9 = 0;
  v17 = 0;
  *(_DWORD *)&v21[8] = 0;
  for ( *(_QWORD *)v21 = (unsigned int)(a4 != 0) + 1; v9 < a2; ++v9 )
  {
    v10 = v9;
    if ( a3[v10].fCritical == a4 )
    {
      if ( !(unsigned int)MyGetOIDInfo(v22, 0x300u, a3[v10].pszObjId) )
        return;
      lParam_4 = *a5;
      *a5 = lParam_4 + 1;
      v11 = -1;
      do
        ++v11;
      while ( v22[v11] );
      cbData = a3[v10].Value.cbData;
      pbData = a3[v10].Value.pbData;
      pszObjId = a3[v10].pszObjId;
      v20 = v11;
      *(_QWORD *)&v21[4] = MakeListDisplayHelperForExtension(pszObjId, pbData, cbData);
      SendMessageA(hWnd, 0x104Du, 0, (LPARAM)&lParam);
      DisplayExtension(hWnd, a3[v10].pszObjId, a3[v10].Value.pbData, a3[v10].Value.cbData, *a5 - 1);
    }
  }
}

```

## disassembly

```asm
0x180011a28  mov     [rsp-8+arg_8], rbx
0x180011a2d  push    rbp
0x180011a2e  push    rsi
0x180011a2f  push    rdi
0x180011a30  push    r12
0x180011a32  push    r13
0x180011a34  push    r14
0x180011a36  push    r15
0x180011a38  lea     rbp, [rsp-5A0h]
0x180011a40  sub     rsp, 6A0h
0x180011a47  mov     rax, cs:__security_cookie
0x180011a4e  xor     rax, rsp
0x180011a51  mov     [rbp+5D0h+var_40], rax
0x180011a58  mov     r14, [rbp+5D0h+arg_20]
0x180011a5f  mov     r15d, edx
0x180011a62  xor     edx, edx; Val
0x180011a64  mov     rsi, r8
0x180011a67  mov     r13, rcx
0x180011a6a  mov     r12d, r9d
0x180011a6d  lea     rcx, [rsp+6D0h+lParam]; void *
0x180011a72  lea     r8d, [rdx+58h]; Size
0x180011a76  call    memset_0
0x180011a7b  xor     edx, edx
0x180011a7d  mov     dword ptr [rsp+6D0h+lParam], 0Fh
0x180011a85  lea     rax, [rbp+5D0h+var_640]
0x180011a89  mov     [rsp+6D0h+var_694], rdx
0x180011a8e  mov     [rsp+6D0h+var_688], rax
0x180011a93  mov     edi, edx
0x180011a95  mov     eax, r12d
0x180011a98  mov     [rsp+6D0h+var_698], edx
0x180011a9c  neg     eax
0x180011a9e  mov     [rsp+6D0h+var_678], rdx
0x180011aa3  sbb     ecx, ecx
0x180011aa5  neg     ecx
0x180011aa7  inc     ecx
0x180011aa9  mov     [rsp+6D0h+var_67C], ecx
0x180011aad  test    r15d, r15d
0x180011ab0  jz      loc_180011B58
0x180011ab6  mov     ebx, edi
0x180011ab8  shl     rbx, 5
0x180011abc  cmp     [rbx+rsi+8], r12d
0x180011ac1  jnz     loc_180011B4D
0x180011ac7  mov     r8, [rbx+rsi]; lpMultiByteStr
0x180011acb  lea     rcx, [rbp+5D0h+var_640]; unsigned __int16 *
0x180011acf  mov     edx, 300h; unsigned int
0x180011ad4  call    ?MyGetOIDInfo@@YAHPEAGKPEAD@Z; MyGetOIDInfo(ushort *,ulong,char *)
0x180011ad9  xor     ecx, ecx
0x180011adb  test    eax, eax
0x180011add  jz      short loc_180011B58
0x180011adf  mov     eax, [r14]
0x180011ae2  lea     rdx, [rbp+5D0h+var_640]
0x180011ae6  mov     dword ptr [rsp+6D0h+lParam+4], eax
0x180011aea  inc     eax
0x180011aec  mov     [r14], eax
0x180011aef  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011af3  inc     rax
0x180011af6  cmp     [rdx+rax*2], cx
0x180011afa  jnz     short loc_180011AF3
0x180011afc  mov     r8d, [rbx+rsi+10h]; unsigned int
0x180011b01  mov     rdx, [rbx+rsi+18h]; Src
0x180011b06  mov     rcx, [rbx+rsi]; lpszStructType
0x180011b0a  mov     [rsp+6D0h+var_680], eax
0x180011b0e  call    ?MakeListDisplayHelperForExtension@@YAPEAU_LIST_DISPLAY_HELPER@@PEADPEAEK@Z; MakeListDisplayHelperForExtension(char *,uchar *,ulong)
0x180011b13  lea     r9, [rsp+6D0h+lParam]; lParam
0x180011b18  mov     [rsp+6D0h+var_678], rax
0x180011b1d  xor     r8d, r8d; wParam
0x180011b20  mov     edx, 104Dh; Msg
0x180011b25  mov     rcx, r13; hWnd
0x180011b28  call    cs:__imp_SendMessageA
0x180011b2e  mov     eax, [r14]
0x180011b31  mov     rcx, r13; hWnd
0x180011b34  mov     r9d, [rbx+rsi+10h]; cbEncoded
0x180011b39  dec     eax
0x180011b3b  mov     r8, [rbx+rsi+18h]; pbEncoded
0x180011b40  mov     rdx, [rbx+rsi]; lpszStructType
0x180011b44  mov     [rsp+6D0h+var_6B0], eax; int
0x180011b48  call    DisplayExtension
0x180011b4d  inc     edi
0x180011b4f  cmp     edi, r15d
0x180011b52  jb      loc_180011AB6
0x180011b58  mov     rcx, [rbp+5D0h+var_40]
0x180011b5f  xor     rcx, rsp; StackCookie
0x180011b62  call    __security_check_cookie
0x180011b67  mov     rbx, [rsp+6D0h+arg_8]
0x180011b6f  add     rsp, 6A0h
0x180011b76  pop     r15
0x180011b78  pop     r14
0x180011b7a  pop     r13
0x180011b7c  pop     r12
0x180011b7e  pop     rdi
0x180011b7f  pop     rsi
0x180011b80  pop     rbp
0x180011b81  retn
```
