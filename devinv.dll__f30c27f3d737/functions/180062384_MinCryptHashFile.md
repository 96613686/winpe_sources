# MinCryptHashFile

- ea: `0x180062384`
- end: `0x18006246f`
- name: `MinCryptHashFile`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180062478`

## callees

- `0x180062384`
- `0x180062d58`
- `0x18010cb94`
- `0x18010d2b4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006245e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006245e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180062443`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180062443`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800623ea`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800623ea`

## pseudocode

```c
__int64 __fastcall MinCryptHashFile(
        __int64 a1,
        WCHAR *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        BCRYPT_ALG_HANDLE phAlgorithm)
{
  unsigned int *v5; // rsi
  const WCHAR *v8; // rax
  unsigned int v10; // edi
  int v11; // ebx
  struct HASHLIB_CERT_INFO *v12; // [rsp+28h] [rbp-60h]
  unsigned __int8 *v13; // [rsp+30h] [rbp-58h]
  HANDLE hObject; // [rsp+40h] [rbp-48h] BYREF
  void *v15[2]; // [rsp+48h] [rbp-40h] BYREF

  v5 = (unsigned int *)phAlgorithm;
  hObject = (HANDLE)-1LL;
  *(_OWORD *)v15 = 0;
  *(_DWORD *)phAlgorithm = 0;
  v8 = CapiAlgIdToCngAlgId(a3);
  if ( !v8 )
    return 2148073480LL;
  phAlgorithm = 0;
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, v8, L"Microsoft Primitive Provider", 0) < 0 )
    return 2148073474LL;
  v10 = I_MinCryptMapFile(3, a2, (__int64)v15, &hObject);
  if ( !v10 )
  {
    v11 = HashComputeImageHash(phAlgorithm, v15[1], (unsigned int)v15[0], a4, v5, v12, v13);
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    if ( v11 < 0 )
      v10 = -2146893822;
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return v10;
}

```

## disassembly

```asm
0x180062384  push    rbx
0x180062386  push    rbp
0x180062387  push    rsi
0x180062388  push    rdi
0x180062389  sub     rsp, 68h
0x18006238d  mov     rsi, [rsp+88h+phAlgorithm]
0x180062395  xorps   xmm0, xmm0
0x180062398  mov     ecx, r8d; unsigned int
0x18006239b  mov     [rsp+88h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800623a4  mov     rbp, r9
0x1800623a7  mov     rbx, rdx
0x1800623aa  movups  xmmword ptr [rsp+88h+var_40], xmm0
0x1800623af  mov     dword ptr [rsi], 0
0x1800623b5  call    ?CapiAlgIdToCngAlgId@@YAPEBGI@Z; CapiAlgIdToCngAlgId(uint)
0x1800623ba  test    rax, rax
0x1800623bd  jnz     short loc_1800623C9
0x1800623bf  mov     eax, 80090008h
0x1800623c4  jmp     loc_180062466
0x1800623c9  xor     r9d, r9d; dwFlags
0x1800623cc  mov     [rsp+88h+phAlgorithm], 0
0x1800623d8  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800623df  mov     rdx, rax; pszAlgId
0x1800623e2  lea     rcx, [rsp+88h+phAlgorithm]; phAlgorithm
0x1800623ea  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800623f0  test    eax, eax
0x1800623f2  jns     short loc_1800623FB
0x1800623f4  mov     eax, 80090002h
0x1800623f9  jmp     short loc_180062466
0x1800623fb  lea     r9, [rsp+88h+hObject]
0x180062400  mov     rdx, rbx
0x180062403  lea     r8, [rsp+88h+var_40]
0x180062408  mov     ecx, 3
0x18006240d  call    I_MinCryptMapFile
0x180062412  mov     edi, eax
0x180062414  test    eax, eax
0x180062416  jnz     short loc_180062453
0x180062418  mov     r8d, dword ptr [rsp+88h+var_40]; unsigned int
0x18006241d  mov     r9, rbp; unsigned __int8 *
0x180062420  mov     rdx, [rsp+88h+var_40+8]; void *
0x180062425  mov     rcx, [rsp+88h+phAlgorithm]; void *
0x18006242d  mov     [rsp+88h+var_68], rsi; unsigned int *
0x180062432  call    ?HashComputeImageHash@@YAJPEAXPEBXKPEAEPEAKPEAUHASHLIB_CERT_INFO@@2@Z; HashComputeImageHash(void *,void const *,ulong,uchar *,ulong *,HASHLIB_CERT_INFO *,uchar *)
0x180062437  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x18006243f  xor     edx, edx; dwFlags
0x180062441  mov     ebx, eax
0x180062443  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180062449  test    ebx, ebx
0x18006244b  mov     eax, 80090002h
0x180062450  cmovs   edi, eax
0x180062453  mov     rcx, [rsp+88h+hObject]; hObject
0x180062458  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006245c  jz      short loc_180062464
0x18006245e  call    cs:__imp_CloseHandle
0x180062464  mov     eax, edi
0x180062466  add     rsp, 68h
0x18006246a  pop     rdi
0x18006246b  pop     rsi
0x18006246c  pop     rbp
0x18006246d  pop     rbx
0x18006246e  retn
```
