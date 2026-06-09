# CACHED_FILE_KEY::GetIsEqual(IHttpCacheKey *)

- ea: `0x180003ad0`
- end: `0x180003b31`
- name: `?GetIsEqual@CACHED_FILE_KEY@@UEBA_NPEAVIHttpCacheKey@@@Z`
- size: `97`
- prototype: `bool __fastcall(CACHED_FILE_KEY *__hidden this, struct IHttpCacheKey *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003ad0`
- `0x180004010`

## pseudocode

```c
bool __fastcall CACHED_FILE_KEY::GetIsEqual(CACHED_FILE_KEY *this, struct IHttpCacheKey *a2)
{
  __int64 (__fastcall *v3)(CACHED_FILE_KEY *); // rbx
  __int64 v4; // rsi
  unsigned __int16 *v5; // rax
  __int64 v6; // rsi
  int v7; // edx
  int v8; // ecx

  v3 = *(__int64 (__fastcall **)(CACHED_FILE_KEY *))(*(_QWORD *)this + 40LL);
  v4 = (*(__int64 (__fastcall **)(struct IHttpCacheKey *))(*(_QWORD *)a2 + 40LL))(a2);
  v5 = (unsigned __int16 *)v3(this);
  v6 = v4 - (_QWORD)v5;
  do
  {
    v7 = *(unsigned __int16 *)((char *)v5 + v6);
    v8 = *v5 - v7;
    if ( v8 )
      break;
    ++v5;
  }
  while ( v7 );
  return v8 == 0;
}

```

## disassembly

```asm
0x180003ad0  mov     [rsp+arg_0], rbx
0x180003ad5  mov     [rsp+arg_8], rsi
0x180003ada  push    rdi
0x180003adb  sub     rsp, 20h
0x180003adf  mov     r8, [rcx]
0x180003ae2  mov     rdi, rcx
0x180003ae5  mov     rax, [rdx]
0x180003ae8  mov     rcx, rdx
0x180003aeb  mov     rbx, [r8+28h]
0x180003aef  mov     rax, [rax+28h]
0x180003af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003af8  mov     rsi, rax
0x180003afb  mov     rcx, rdi
0x180003afe  mov     rax, rbx
0x180003b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b06  sub     rsi, rax
0x180003b09  movzx   ecx, word ptr [rax]
0x180003b0c  movzx   edx, word ptr [rax+rsi]
0x180003b10  sub     ecx, edx
0x180003b12  jnz     short loc_180003B1C
0x180003b14  add     rax, 2
0x180003b18  test    edx, edx
0x180003b1a  jnz     short loc_180003B09
0x180003b1c  mov     rbx, [rsp+28h+arg_0]
0x180003b21  test    ecx, ecx
0x180003b23  mov     rsi, [rsp+28h+arg_8]
0x180003b28  setz    al
0x180003b2b  add     rsp, 20h
0x180003b2f  pop     rdi
0x180003b30  retn
```
