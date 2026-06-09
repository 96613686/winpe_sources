# SslEmptyNCryptProvCache

- ea: `0x180012978`
- end: `0x1800129ed`
- name: `SslEmptyNCryptProvCache`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012838`

## callees

- `0x180003ef0`
- `0x180012978`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x1800129c6`
- `ncrypt!NCryptFreeObject` at `0x1800129c6`
- `ntdll!RtlDeleteResource` at `0x1800129b3`

## pseudocode

```c
void __fastcall SslEmptyNCryptProvCache(__int64 a1)
{
  _QWORD *v1; // rbx
  NCRYPT_HANDLE v3; // rcx
  _QWORD *v4; // rsi

  v1 = *(_QWORD **)a1;
  *(_QWORD *)a1 = 0;
  if ( v1 )
  {
    do
    {
      v3 = v1[2];
      v4 = (_QWORD *)*v1;
      if ( v3 )
      {
        NCryptFreeObject(v3);
        v1[2] = 0;
      }
      *v1 = 0;
      MSCryptFree(v1);
      v1 = v4;
    }
    while ( v4 );
  }
  *(_DWORD *)(a1 + 16) = 0;
  RtlDeleteResource((PRTL_RESOURCE)(a1 + 24));
}

```

## disassembly

```asm
0x180012978  mov     [rsp+arg_0], rbx
0x18001297d  mov     [rsp+arg_8], rsi
0x180012982  push    rdi
0x180012983  sub     rsp, 20h
0x180012987  mov     rbx, [rcx]
0x18001298a  mov     rdi, rcx
0x18001298d  mov     qword ptr [rcx], 0
0x180012994  test    rbx, rbx
0x180012997  jnz     short loc_1800129BA
0x180012999  lea     rcx, [rdi+18h]
0x18001299d  mov     dword ptr [rdi+10h], 0
0x1800129a4  mov     rbx, [rsp+28h+arg_0]
0x1800129a9  mov     rsi, [rsp+28h+arg_8]
0x1800129ae  add     rsp, 20h
0x1800129b2  pop     rdi
0x1800129b3  jmp     cs:__imp_RtlDeleteResource
0x1800129ba  mov     rcx, [rbx+10h]; hObject
0x1800129be  mov     rsi, [rbx]
0x1800129c1  test    rcx, rcx
0x1800129c4  jz      short loc_1800129D4
0x1800129c6  call    cs:__imp_NCryptFreeObject
0x1800129cc  mov     qword ptr [rbx+10h], 0
0x1800129d4  mov     rcx, rbx
0x1800129d7  mov     qword ptr [rbx], 0
0x1800129de  call    MSCryptFree
0x1800129e3  mov     rbx, rsi
0x1800129e6  test    rsi, rsi
0x1800129e9  jnz     short loc_1800129BA
0x1800129eb  jmp     short loc_180012999
```
