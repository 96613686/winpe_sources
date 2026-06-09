# DfsGetClusterResourceNetworkName(_HRESOURCE *,_UNICODE_STRING *,_UNICODE_STRING *,uchar)

- ea: `0x140013550`
- end: `0x14001385d`
- name: `?DfsGetClusterResourceNetworkName@@YAKPEAU_HRESOURCE@@PEAU_UNICODE_STRING@@1E@Z`
- size: `781`
- prototype: `unsigned int __fastcall(struct _HRESOURCE *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140012d10`

## callees

- `0x1400133cc`
- `0x140013550`
- `0x140058db8`
- `0x14005ce22`
- `0x14005ce70`

## import_xrefs

- `msvcrt!printf` at `0x140013718`
- `msvcrt!printf` at `0x140013718`
- `msvcrt!wcschr` at `0x140013783`
- `msvcrt!wcschr` at `0x140013783`
- `msvcrt!free` at `0x14001380c`
- `msvcrt!free` at `0x14001380c`
- `msvcrt!malloc` at `0x1400135e8`
- `msvcrt!malloc` at `0x140013625`
- `msvcrt!malloc` at `0x1400136fd`
- `msvcrt!malloc` at `0x1400137c8`
- `msvcrt!malloc` at `0x1400135e8`
- `msvcrt!malloc` at `0x140013625`
- `msvcrt!malloc` at `0x1400136fd`
- `msvcrt!malloc` at `0x1400137c8`
- `ntdll!RtlInitUnicodeString` at `0x140013595`
- `ntdll!RtlInitUnicodeString` at `0x140013595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013689`
- `CLUSAPI!ClusterControl` at `0x1400136c7`
- `CLUSAPI!ClusterControl` at `0x140013751`
- `CLUSAPI!ClusterControl` at `0x1400136c7`
- `CLUSAPI!ClusterControl` at `0x140013751`
- `CLUSAPI!GetClusterResourceNetworkName` at `0x1400135b6`
- `CLUSAPI!GetClusterResourceNetworkName` at `0x1400135b6`
- `CLUSAPI!CloseCluster` at `0x14001381b`
- `CLUSAPI!CloseCluster` at `0x14001381b`
- `CLUSAPI!OpenCluster` at `0x140013675`
- `CLUSAPI!OpenCluster` at `0x140013675`

## pseudocode

```c
__int64 __fastcall DfsGetClusterResourceNetworkName(
        struct _HRESOURCE *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        char a4)
{
  DWORD LastError; // edi
  struct _UNICODE_STRING *v8; // rsi
  USHORT v9; // cx
  size_t v10; // rbx
  WCHAR *v11; // rax
  WCHAR *v12; // rax
  struct _HCLUSTER *v13; // r12
  DWORD v14; // eax
  DWORD nOutBufferSize; // ebx
  void *lpOutBuffer; // r14
  wchar_t *v17; // rax
  wchar_t *v18; // r13
  size_t v19; // rbx
  DWORD v20; // esi
  size_t v21; // rcx
  WCHAR *v22; // rax
  DWORD nSize; // [rsp+40h] [rbp-89h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-85h] BYREF
  size_t Size; // [rsp+48h] [rbp-81h]
  struct _UNICODE_STRING *v27; // [rsp+50h] [rbp-79h]
  WCHAR Buffer[64]; // [rsp+60h] [rbp-69h] BYREF

  v27 = a3;
  LastError = 0;
  BytesReturned = 0;
  v8 = a3;
  RtlInitUnicodeString(a3, 0);
  nSize = 64;
  if ( !GetClusterResourceNetworkName(a1, Buffer, &nSize) )
  {
LABEL_9:
    LastError = GetLastError();
    goto LABEL_28;
  }
  v9 = 2 * nSize;
  v10 = (unsigned __int16)(2 * nSize + 2);
  if ( a4 )
  {
    v8->Length = v9;
    v8->MaximumLength = v10;
    v12 = (WCHAR *)malloc((unsigned __int16)(v9 + 2));
    v8->Buffer = v12;
    if ( !v12 )
      goto LABEL_4;
    memcpy_0(v12, Buffer, v10);
    nSize = 64;
    LastError = DfsGetClusterResourceNetworkDnsName(a1, Buffer, &nSize);
    if ( LastError )
      goto LABEL_28;
    LODWORD(Size) = 2 * nSize;
    v13 = OpenCluster(0);
    if ( !v13 )
      goto LABEL_9;
    v14 = ClusterControl(v13, 0, 0x700003Du, 0, 0, 0, 0, &BytesReturned);
    nOutBufferSize = BytesReturned;
    LastError = v14;
    if ( v14 )
    {
      if ( v14 != 234 )
        goto LABEL_27;
    }
    else if ( !BytesReturned )
    {
      LastError = 5007;
LABEL_27:
      CloseCluster(v13);
LABEL_28:
      if ( LastError )
        goto LABEL_29;
      return LastError;
    }
    nSize = BytesReturned;
    lpOutBuffer = malloc(BytesReturned);
    if ( lpOutBuffer )
    {
      LastError = ClusterControl(v13, 0, 0x700003Du, 0, 0, lpOutBuffer, nOutBufferSize, &BytesReturned);
      if ( !LastError )
      {
        if ( BytesReturned < 0xFFFF && (v17 = wcschr((const wchar_t *)lpOutBuffer, 0x2Eu), (v18 = v17) != 0) )
        {
          v19 = (unsigned int)Size;
          v20 = BytesReturned + (_DWORD)lpOutBuffer - (_DWORD)v17;
          if ( v20 + (unsigned int)Size < 0xFFFF )
          {
            v21 = (unsigned __int16)(BytesReturned + (_WORD)lpOutBuffer - (_WORD)v17 + Size);
            a2->MaximumLength = v21;
            a2->Length = v21 - 2;
            v22 = (WCHAR *)malloc(v21);
            a2->Buffer = v22;
            if ( v22 )
            {
              memcpy_0(v22, Buffer, v19);
              memcpy_0((char *)a2->Buffer + v19, v18, v20);
            }
            else
            {
              LastError = 1450;
            }
          }
          else
          {
            LastError = 5007;
          }
          v8 = v27;
        }
        else
        {
          LastError = 5007;
        }
      }
      free(lpOutBuffer);
    }
    else
    {
      printf("no mem\n");
      LastError = 1450;
    }
    goto LABEL_27;
  }
  a2->Length = v9;
  a2->MaximumLength = v10;
  v11 = (WCHAR *)malloc((unsigned __int16)(v9 + 2));
  a2->Buffer = v11;
  if ( !v11 )
  {
LABEL_4:
    LastError = 1450;
LABEL_29:
    DfsFreeUnicodeString(v8);
    return LastError;
  }
  memcpy_0(v11, Buffer, v10);
  return LastError;
}

```

## disassembly

```asm
0x140013550  mov     [rsp-8+arg_18], rbx
0x140013555  push    rbp
0x140013556  push    rsi
0x140013557  push    rdi
0x140013558  push    r12
0x14001355a  push    r13
0x14001355c  push    r14
0x14001355e  push    r15
0x140013560  lea     rbp, [rsp-27h]
0x140013565  sub     rsp, 0F0h
0x14001356c  mov     rax, cs:__security_cookie
0x140013573  xor     rax, rsp
0x140013576  mov     [rbp+57h+var_40], rax
0x14001357a  mov     r15, rdx
0x14001357d  mov     [rbp+57h+var_D0], r8
0x140013581  mov     r12, rcx
0x140013584  xor     edi, edi
0x140013586  and     [rsp+120h+BytesReturned], edi
0x14001358a  xor     edx, edx; SourceString
0x14001358c  mov     rcx, r8; DestinationString
0x14001358f  mov     r14b, r9b
0x140013592  mov     rsi, r8
0x140013595  call    cs:__imp_RtlInitUnicodeString
0x14001359c  nop     dword ptr [rax+rax+00h]
0x1400135a1  lea     r13d, [rdi+40h]
0x1400135a5  mov     rcx, r12; hResource
0x1400135a8  lea     r8, [rsp+120h+nSize]; nSize
0x1400135ad  mov     [rsp+120h+nSize], r13d
0x1400135b2  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x1400135b6  call    cs:__imp_GetClusterResourceNetworkName
0x1400135bd  nop     dword ptr [rax+rax+00h]
0x1400135c2  test    eax, eax
0x1400135c4  jz      loc_140013689
0x1400135ca  movzx   ecx, word ptr [rsp+120h+nSize]
0x1400135cf  add     cx, cx
0x1400135d2  lea     eax, [rcx+2]
0x1400135d5  movzx   ebx, ax
0x1400135d8  test    r14b, r14b
0x1400135db  jnz     short loc_14001361B
0x1400135dd  mov     [r15], cx
0x1400135e1  mov     ecx, ebx; Size
0x1400135e3  mov     [r15+2], bx
0x1400135e8  call    cs:__imp_malloc
0x1400135ef  nop     dword ptr [rax+rax+00h]
0x1400135f4  mov     [r15+8], rax
0x1400135f8  test    rax, rax
0x1400135fb  jnz     short loc_140013607
0x1400135fd  mov     edi, 5AAh
0x140013602  jmp     loc_14001382B
0x140013607  mov     r8, rbx; Size
0x14001360a  lea     rdx, [rbp+57h+Buffer]; Src
0x14001360e  mov     rcx, rax; void *
0x140013611  call    memcpy_0
0x140013616  jmp     loc_140013833
0x14001361b  mov     [rsi], cx
0x14001361e  mov     rcx, rbx; Size
0x140013621  mov     [rsi+2], bx
0x140013625  call    cs:__imp_malloc
0x14001362c  nop     dword ptr [rax+rax+00h]
0x140013631  mov     [rsi+8], rax
0x140013635  test    rax, rax
0x140013638  jz      short loc_1400135FD
0x14001363a  mov     r8, rbx; Size
0x14001363d  lea     rdx, [rbp+57h+Buffer]; Src
0x140013641  mov     rcx, rax; void *
0x140013644  call    memcpy_0
0x140013649  lea     r8, [rsp+120h+nSize]; unsigned int *
0x14001364e  mov     [rsp+120h+nSize], r13d
0x140013653  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x140013657  mov     rcx, r12; struct _HRESOURCE *
0x14001365a  call    ?DfsGetClusterResourceNetworkDnsName@@YAKPEAU_HRESOURCE@@PEAGPEAK@Z; DfsGetClusterResourceNetworkDnsName(_HRESOURCE *,ushort *,ulong *)
0x14001365f  mov     edi, eax
0x140013661  test    eax, eax
0x140013663  jnz     loc_140013827
0x140013669  mov     eax, [rsp+120h+nSize]
0x14001366d  xor     ecx, ecx; lpszClusterName
0x14001366f  add     eax, eax
0x140013671  mov     dword ptr [rsp+120h+Size], eax
0x140013675  call    cs:__imp_OpenCluster
0x14001367c  nop     dword ptr [rax+rax+00h]
0x140013681  mov     r12, rax
0x140013684  test    rax, rax
0x140013687  jnz     short loc_14001369C
0x140013689  call    cs:__imp_GetLastError
0x140013690  nop     dword ptr [rax+rax+00h]
0x140013695  mov     edi, eax
0x140013697  jmp     loc_140013827
0x14001369c  lea     rax, [rsp+120h+BytesReturned]
0x1400136a1  mov     r13d, 700003Dh
0x1400136a7  mov     [rsp+120h+lpBytesReturned], rax; lpBytesReturned
0x1400136ac  xor     r9d, r9d; lpInBuffer
0x1400136af  and     [rsp+120h+nOutBufferSize], 0
0x1400136b4  mov     r8d, r13d; dwControlCode
0x1400136b7  and     [rsp+120h+lpOutBuffer], 0
0x1400136bd  xor     edx, edx; hHostNode
0x1400136bf  and     [rsp+120h+var_100], 0
0x1400136c4  mov     rcx, r12; hCluster
0x1400136c7  call    cs:__imp_ClusterControl
0x1400136ce  nop     dword ptr [rax+rax+00h]
0x1400136d3  mov     ebx, [rsp+120h+BytesReturned]
0x1400136d7  mov     edi, eax
0x1400136d9  test    eax, eax
0x1400136db  jnz     short loc_1400136EB
0x1400136dd  test    ebx, ebx
0x1400136df  jnz     short loc_1400136F6
0x1400136e1  mov     edi, 138Fh
0x1400136e6  jmp     loc_140013818
0x1400136eb  cmp     eax, 0EAh
0x1400136f0  jnz     loc_140013818
0x1400136f6  mov     rcx, rbx; Size
0x1400136f9  mov     [rsp+120h+nSize], ebx
0x1400136fd  call    cs:__imp_malloc
0x140013704  nop     dword ptr [rax+rax+00h]
0x140013709  mov     r14, rax
0x14001370c  test    rax, rax
0x14001370f  jnz     short loc_14001372E
0x140013711  lea     rcx, Format; "no mem\n"
0x140013718  call    cs:__imp_printf
0x14001371f  nop     dword ptr [rax+rax+00h]
0x140013724  mov     edi, 5AAh
0x140013729  jmp     loc_140013818
0x14001372e  lea     rax, [rsp+120h+BytesReturned]
0x140013733  xor     r9d, r9d; lpInBuffer
0x140013736  mov     [rsp+120h+lpBytesReturned], rax; lpBytesReturned
0x14001373b  mov     r8d, r13d; dwControlCode
0x14001373e  mov     [rsp+120h+nOutBufferSize], ebx; nOutBufferSize
0x140013742  xor     edx, edx; hHostNode
0x140013744  mov     [rsp+120h+lpOutBuffer], r14; lpOutBuffer
0x140013749  mov     rcx, r12; hCluster
0x14001374c  and     [rsp+120h+var_100], 0
0x140013751  call    cs:__imp_ClusterControl
0x140013758  nop     dword ptr [rax+rax+00h]
0x14001375d  mov     edi, eax
0x14001375f  test    eax, eax
0x140013761  jnz     loc_140013809
0x140013767  cmp     [rsp+120h+BytesReturned], 0FFFFh
0x14001376f  jb      short loc_14001377B
0x140013771  mov     edi, 138Fh
0x140013776  jmp     loc_140013809
0x14001377b  mov     edx, 2Eh ; '.'; Ch
0x140013780  mov     rcx, r14; Str
0x140013783  call    cs:__imp_wcschr
0x14001378a  nop     dword ptr [rax+rax+00h]
0x14001378f  mov     r13, rax
0x140013792  test    rax, rax
0x140013795  jz      short loc_140013771
0x140013797  mov     ebx, dword ptr [rsp+120h+Size]
0x14001379b  mov     esi, r14d
0x14001379e  sub     esi, r13d
0x1400137a1  add     esi, [rsp+120h+BytesReturned]
0x1400137a5  lea     eax, [rsi+rbx]
0x1400137a8  cmp     eax, 0FFFFh
0x1400137ad  jb      short loc_1400137B6
0x1400137af  mov     edi, 138Fh
0x1400137b4  jmp     short loc_140013805
0x1400137b6  lea     eax, [rsi+rbx]
0x1400137b9  movzx   ecx, ax; Size
0x1400137bc  mov     [r15+2], cx
0x1400137c1  lea     eax, [rcx-2]
0x1400137c4  mov     [r15], ax
0x1400137c8  call    cs:__imp_malloc
0x1400137cf  nop     dword ptr [rax+rax+00h]
0x1400137d4  mov     [r15+8], rax
0x1400137d8  test    rax, rax
0x1400137db  jnz     short loc_1400137E4
0x1400137dd  mov     edi, 5AAh
0x1400137e2  jmp     short loc_140013805
0x1400137e4  mov     r8, rbx; Size
0x1400137e7  lea     rdx, [rbp+57h+Buffer]; Src
0x1400137eb  mov     rcx, rax; void *
0x1400137ee  call    memcpy_0
0x1400137f3  mov     rcx, [r15+8]
0x1400137f7  mov     rdx, r13; Src
0x1400137fa  add     rcx, rbx; void *
0x1400137fd  mov     r8d, esi; Size
0x140013800  call    memcpy_0
0x140013805  mov     rsi, [rbp+57h+var_D0]
0x140013809  mov     rcx, r14; Block
0x14001380c  call    cs:__imp_free
0x140013813  nop     dword ptr [rax+rax+00h]
0x140013818  mov     rcx, r12; hCluster
0x14001381b  call    cs:__imp_CloseCluster
0x140013822  nop     dword ptr [rax+rax+00h]
0x140013827  test    edi, edi
0x140013829  jz      short loc_140013833
0x14001382b  mov     rcx, rsi
0x14001382e  call    DfsFreeUnicodeString
0x140013833  mov     eax, edi
0x140013835  mov     rcx, [rbp+57h+var_40]
0x140013839  xor     rcx, rsp; StackCookie
0x14001383c  call    __security_check_cookie
0x140013841  mov     rbx, [rsp+120h+arg_18]
0x140013849  add     rsp, 0F0h
0x140013850  pop     r15
0x140013852  pop     r14
0x140013854  pop     r13
0x140013856  pop     r12
0x140013858  pop     rdi
0x140013859  pop     rsi
0x14001385a  pop     rbp
0x14001385b  retn
```
