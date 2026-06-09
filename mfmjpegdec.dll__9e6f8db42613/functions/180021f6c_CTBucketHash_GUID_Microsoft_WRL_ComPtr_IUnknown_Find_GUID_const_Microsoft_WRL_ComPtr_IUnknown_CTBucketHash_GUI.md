# CTBucketHash<_GUID,Microsoft::WRL::ComPtr<IUnknown>>::Find(_GUID const &,Microsoft::WRL::ComPtr<IUnknown> &,CTBucketHash<_GUID,Microsoft::WRL::ComPtr<IUnknown>>::_POSITION &)

- ea: `0x180021f6c`
- end: `0x180021fe3`
- name: `?Find@?$CTBucketHash@U_GUID@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@@QEAAHAEBU_GUID@@AEAV?$ComPtr@UIUnknown@@@WRL@Microsoft@@AEAU_POSITION@1@@Z`
- size: `119`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022210`
- `0x18005f1f4`
- `0x18005f7b0`

## callees

- `0x180021f6c`
- `0x180021fec`

## pseudocode

```c
_BOOL8 __fastcall CTBucketHash<_GUID,Microsoft::WRL::ComPtr<IUnknown>>::Find(
        __int64 *a1,
        __int64 a2,
        __int64 *a3,
        _QWORD *a4)
{
  __int64 v4; // rbx
  __int64 v7; // rdx
  _QWORD *i; // rbx
  __int64 v9; // rax

  v4 = *a1;
  if ( !*a1 )
    return 0;
  v7 = *(_DWORD *)a2 % ((_DWORD)a1[1] & 0x7FFFFFFFu);
  *a4 = 0;
  a4[1] = 0;
  for ( i = *(_QWORD **)(v4 + 8 * v7); i; i = (_QWORD *)i[3] )
  {
    v9 = *i - *(_QWORD *)a2;
    if ( *i == *(_QWORD *)a2 )
      v9 = i[1] - *(_QWORD *)(a2 + 8);
    if ( !v9 )
    {
      *a4 = i;
      Microsoft::WRL::ComPtr<ID3D12Resource>::operator=(a3, i + 2);
      return i != 0;
    }
    a4[1] = i;
  }
  return i != 0;
}

```

## disassembly

```asm
0x180021f6c  push    rbx
0x180021f6e  sub     rsp, 20h
0x180021f72  mov     rbx, [rcx]
0x180021f75  mov     r10, rdx
0x180021f78  test    rbx, rbx
0x180021f7b  jnz     short loc_180021F81
0x180021f7d  xor     eax, eax
0x180021f7f  jmp     short loc_180021FDD
0x180021f81  mov     ecx, [rcx+8]
0x180021f84  xor     edx, edx
0x180021f86  mov     eax, [r10]
0x180021f89  btr     ecx, 1Fh
0x180021f8d  div     ecx
0x180021f8f  mov     qword ptr [r9], 0
0x180021f96  mov     qword ptr [r9+8], 0
0x180021f9e  mov     rbx, [rbx+rdx*8]
0x180021fa2  test    rbx, rbx
0x180021fa5  jz      short loc_180021FD5
0x180021fa7  mov     rax, [rbx]
0x180021faa  sub     rax, [r10]
0x180021fad  jnz     short loc_180021FB7
0x180021faf  mov     rax, [rbx+8]
0x180021fb3  sub     rax, [r10+8]
0x180021fb7  test    rax, rax
0x180021fba  jz      short loc_180021FC6
0x180021fbc  mov     [r9+8], rbx
0x180021fc0  mov     rbx, [rbx+18h]
0x180021fc4  jmp     short loc_180021FA2
0x180021fc6  lea     rdx, [rbx+10h]
0x180021fca  mov     [r9], rbx
0x180021fcd  mov     rcx, r8
0x180021fd0  call    ??4?$ComPtr@UID3D12Resource@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ID3D12Resource>::operator=(Microsoft::WRL::ComPtr<ID3D12Resource> const &)
0x180021fd5  xor     eax, eax
0x180021fd7  test    rbx, rbx
0x180021fda  setnz   al
0x180021fdd  add     rsp, 20h
0x180021fe1  pop     rbx
0x180021fe2  retn
```
