# GmsapConcatenate(int,ushort * *,ushort,...)

- ea: `0x1800066ac`
- end: `0x180006863`
- name: `?GmsapConcatenate@@YAJHPEAPEAGGZZ`
- size: `439`
- prototype: `__int64(int, unsigned __int16 **, unsigned __int16, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006a38`

## callees

- `0x180001c8a`
- `0x1800052d0`
- `0x1800066ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006745`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006745`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000682e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000682e`
- `netutils!NetApiBufferFree` at `0x18000683c`
- `netutils!NetApiBufferFree` at `0x18000683c`
- `netutils!NetApiBufferAllocate` at `0x180006784`
- `netutils!NetApiBufferAllocate` at `0x180006784`

## pseudocode

```c
__int64 GmsapConcatenate(int a1, unsigned __int16 **a2, unsigned __int16 a3, ...)
{
  va_list v5; // rdx
  unsigned __int16 v6; // bx
  unsigned __int16 i; // cx
  __int64 v8; // r9
  __int64 v9; // rax
  unsigned __int16 v10; // ax
  unsigned __int16 v11; // bx
  unsigned __int64 v12; // rsi
  void *v13; // rcx
  int j; // ebx
  DWORD v15; // ecx
  int v16; // eax
  va_list v17; // r14
  unsigned __int16 v18; // di
  int v19; // eax
  LPVOID Buffer; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 v22; // [rsp+A0h] [rbp+58h]
  va_list va; // [rsp+A8h] [rbp+60h] BYREF

  va_start(va, a3);
  v22 = a3;
  Buffer = 0;
  if ( a2 && a3 >= 2u )
  {
    *a2 = 0;
    va_copy(v5, va);
    v6 = 0;
    for ( i = 0; i < a3; ++i )
    {
      v5 += 8;
      v8 = *((_QWORD *)v5 - 1);
      if ( !v8 )
        return (unsigned int)-1073741811;
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(v8 + 2 * v9) );
      v10 = v6 + v9;
      if ( v10 < v6 )
        return (unsigned int)-1073741675;
      v6 = v10;
    }
    v11 = v10 + 1;
    if ( a1 )
    {
      v12 = v11;
      Buffer = LocalAlloc(0x40u, 2LL * v11);
      v13 = Buffer;
      if ( !Buffer )
      {
        j = -1073741801;
        goto LABEL_28;
      }
    }
    else
    {
      v15 = NetApiBufferAllocate(2 * v11, &Buffer);
      if ( v15 )
      {
        v16 = 0;
        while ( LODWORD(ErrorMap[v16]) != v15 )
        {
          if ( (unsigned int)++v16 >= 0x7A )
          {
            j = -1073741595;
            goto LABEL_20;
          }
        }
        j = HIDWORD(ErrorMap[v16]);
LABEL_20:
        v13 = Buffer;
LABEL_27:
        if ( j >= 0 )
          return (unsigned int)j;
LABEL_28:
        if ( v13 )
        {
          if ( a1 )
            LocalFree(v13);
          else
            NetApiBufferFree(v13);
        }
        return (unsigned int)j;
      }
      v12 = v11;
      memset_0(Buffer, 0, 2LL * v11);
      v13 = Buffer;
    }
    va_copy(v17, va);
    v18 = 0;
    for ( j = 0; v18 < v22; ++v18 )
    {
      v17 += 8;
      if ( !*((_QWORD *)v17 - 1) )
        break;
      v19 = RtlStringCchPrintfW((unsigned __int16 *)v13, v12, L"%ws%ws", v13, *((_QWORD *)v17 - 1));
      v13 = Buffer;
      j = v19;
      if ( v19 < 0 )
        goto LABEL_28;
    }
    *a2 = (unsigned __int16 *)v13;
    goto LABEL_27;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1800066ac  mov     [rsp-40h+arg_10], r8w
0x1800066b2  mov     [rsp-40h+arg_18], r9
0x1800066b7  push    rbp
0x1800066b8  push    rbx
0x1800066b9  push    rsi
0x1800066ba  push    rdi
0x1800066bb  push    r12
0x1800066bd  push    r13
0x1800066bf  push    r14
0x1800066c1  push    r15
0x1800066c3  mov     rbp, rsp
0x1800066c6  sub     rsp, 48h
0x1800066ca  xor     r13d, r13d
0x1800066cd  mov     r15, rdx
0x1800066d0  mov     [rbp+Buffer], r13
0x1800066d4  mov     r12d, ecx
0x1800066d7  test    rdx, rdx
0x1800066da  jz      loc_18000684C
0x1800066e0  cmp     r8w, 2
0x1800066e5  jb      loc_18000684C
0x1800066eb  mov     [rdx], r13
0x1800066ee  lea     rdx, [rbp+arg_18]
0x1800066f2  lea     edi, [r13+1]
0x1800066f6  mov     ebx, r13d
0x1800066f9  mov     ecx, r13d
0x1800066fc  cmp     r13w, r8w
0x180006700  jnb     short loc_180006731
0x180006702  lea     rdx, [rdx+8]
0x180006706  mov     r9, [rdx-8]
0x18000670a  test    r9, r9
0x18000670d  jz      short loc_180006771
0x18000670f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006713  inc     rax
0x180006716  cmp     [r9+rax*2], r13w
0x18000671b  jnz     short loc_180006713
0x18000671d  add     ax, bx
0x180006720  cmp     ax, bx
0x180006723  jb      short loc_180006767
0x180006725  add     cx, di
0x180006728  movzx   ebx, ax
0x18000672b  cmp     cx, r8w
0x18000672f  jb      short loc_180006702
0x180006731  add     bx, di
0x180006734  test    r12d, r12d
0x180006737  jz      short loc_18000677B
0x180006739  movzx   esi, bx
0x18000673c  mov     ecx, 40h ; '@'; uFlags
0x180006741  lea     rdx, [rsi+rsi]; uBytes
0x180006745  call    cs:__imp_LocalAlloc
0x18000674c  nop     dword ptr [rax+rax+00h]
0x180006751  mov     [rbp+Buffer], rax
0x180006755  mov     rcx, rax
0x180006758  test    rax, rax
0x18000675b  jnz     short loc_1800067D5
0x18000675d  mov     ebx, 0C0000017h
0x180006762  jmp     loc_180006824
0x180006767  mov     ebx, 0C0000095h
0x18000676c  jmp     loc_180006848
0x180006771  mov     ebx, 0C000000Dh
0x180006776  jmp     loc_180006848
0x18000677b  movzx   ecx, bx
0x18000677e  lea     rdx, [rbp+Buffer]; Buffer
0x180006782  add     ecx, ecx; ByteCount
0x180006784  call    cs:__imp_NetApiBufferAllocate
0x18000678b  nop     dword ptr [rax+rax+00h]
0x180006790  mov     ecx, eax
0x180006792  test    eax, eax
0x180006794  jz      short loc_1800067BF
0x180006796  mov     eax, r13d
0x180006799  lea     rdx, ErrorMap
0x1800067a0  mov     ebx, eax
0x1800067a2  cmp     [rdx+rbx*8], ecx
0x1800067a5  jz      short loc_1800067B5
0x1800067a7  add     eax, edi
0x1800067a9  cmp     eax, 7Ah ; 'z'
0x1800067ac  jb      short loc_1800067A0
0x1800067ae  mov     ebx, 0C00000E5h
0x1800067b3  jmp     short loc_1800067B9
0x1800067b5  mov     ebx, [rdx+rbx*8+4]
0x1800067b9  mov     rcx, [rbp+Buffer]
0x1800067bd  jmp     short loc_180006820
0x1800067bf  mov     rcx, [rbp+Buffer]; void *
0x1800067c3  xor     edx, edx; Val
0x1800067c5  movzx   esi, bx
0x1800067c8  lea     r8, [rsi+rsi]; Size
0x1800067cc  call    memset_0
0x1800067d1  mov     rcx, [rbp+Buffer]; unsigned __int16 *
0x1800067d5  lea     r14, [rbp+arg_18]
0x1800067d9  mov     edi, r13d
0x1800067dc  mov     ebx, r13d
0x1800067df  cmp     r13w, [rbp+arg_10]
0x1800067e4  jnb     short loc_18000681D
0x1800067e6  lea     r14, [r14+8]
0x1800067ea  mov     rax, [r14-8]
0x1800067ee  test    rax, rax
0x1800067f1  jz      short loc_18000681D
0x1800067f3  mov     r9, rcx
0x1800067f6  mov     [rsp+48h+var_28], rax
0x1800067fb  lea     r8, aWsWs; "%ws%ws"
0x180006802  mov     rdx, rsi; unsigned __int64
0x180006805  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000680a  mov     rcx, [rbp+Buffer]; Buffer
0x18000680e  mov     ebx, eax
0x180006810  test    eax, eax
0x180006812  js      short loc_180006824
0x180006814  inc     di
0x180006817  cmp     di, [rbp+arg_10]
0x18000681b  jb      short loc_1800067E6
0x18000681d  mov     [r15], rcx
0x180006820  test    ebx, ebx
0x180006822  jns     short loc_180006848
0x180006824  test    rcx, rcx
0x180006827  jz      short loc_180006848
0x180006829  test    r12d, r12d
0x18000682c  jz      short loc_18000683C
0x18000682e  call    cs:__imp_LocalFree
0x180006835  nop     dword ptr [rax+rax+00h]
0x18000683a  jmp     short loc_180006848
0x18000683c  call    cs:__imp_NetApiBufferFree
0x180006843  nop     dword ptr [rax+rax+00h]
0x180006848  mov     eax, ebx
0x18000684a  jmp     short loc_180006851
0x18000684c  mov     eax, 0C000000Dh
0x180006851  add     rsp, 48h
0x180006855  pop     r15
0x180006857  pop     r14
0x180006859  pop     r13
0x18000685b  pop     r12
0x18000685d  pop     rdi
0x18000685e  pop     rsi
0x18000685f  pop     rbx
0x180006860  pop     rbp
0x180006861  retn
```
