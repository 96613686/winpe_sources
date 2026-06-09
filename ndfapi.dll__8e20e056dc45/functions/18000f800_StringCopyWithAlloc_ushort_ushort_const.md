# StringCopyWithAlloc(ushort * *,ushort const *)

- ea: `0x18000f800`
- end: `0x18000f899`
- name: `?StringCopyWithAlloc@@YAJPEAPEAGPEBG@Z`
- size: `153`
- prototype: `int(unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000a9e0`
- `0x18000be50`
- `0x18000c0a0`
- `0x18000cde4`
- `0x18000d22c`
- `0x18001c0f0`

## callees

- `0x18000f78c`
- `0x18000f800`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000f861`
- `ole32!CoTaskMemAlloc` at `0x18000f861`

## pseudocode

```c
__int64 __fastcall StringCopyWithAlloc(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // rax
  __int64 v5; // r8
  unsigned int v6; // ecx
  __int64 v7; // rdi
  unsigned __int16 *v8; // rax

  if ( a1 && a2 )
  {
    v4 = a2;
    v5 = 65534;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v5;
    }
    while ( v5 );
    v6 = v5 == 0 ? 0x80070057 : 0;
    v7 = (65534 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * v7 + 2);
      *a1 = v8;
      if ( v8 )
        return (unsigned int)StringCchCopyW(v8, v7 + 1, a2);
      else
        return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x18000f800  push    rbx
0x18000f802  push    rbp
0x18000f803  push    rsi
0x18000f804  push    rdi
0x18000f805  sub     rsp, 28h
0x18000f809  xor     ebp, ebp
0x18000f80b  mov     rbx, rdx
0x18000f80e  mov     rsi, rcx
0x18000f811  test    rcx, rcx
0x18000f814  jz      short loc_18000F889
0x18000f816  test    rdx, rdx
0x18000f819  jz      short loc_18000F889
0x18000f81b  mov     edx, 0FFFEh
0x18000f820  mov     rax, rbx
0x18000f823  mov     r8d, edx
0x18000f826  cmp     [rax], bp
0x18000f829  jz      short loc_18000F835
0x18000f82b  add     rax, 2
0x18000f82f  sub     r8, 1
0x18000f833  jnz     short loc_18000F826
0x18000f835  mov     rax, r8
0x18000f838  neg     rax
0x18000f83b  mov     rax, r8
0x18000f83e  sbb     ecx, ecx
0x18000f840  sub     rdx, r8
0x18000f843  not     ecx
0x18000f845  and     ecx, 80070057h
0x18000f84b  neg     rax
0x18000f84e  sbb     rdi, rdi
0x18000f851  and     rdi, rdx
0x18000f854  test    r8, r8
0x18000f857  jz      short loc_18000F88E
0x18000f859  lea     rcx, ds:2[rdi*2]; cb
0x18000f861  call    cs:__imp_CoTaskMemAlloc
0x18000f867  mov     [rsi], rax
0x18000f86a  test    rax, rax
0x18000f86d  jnz     short loc_18000F876
0x18000f86f  mov     ecx, 8007000Eh
0x18000f874  jmp     short loc_18000F88E
0x18000f876  lea     rdx, [rdi+1]; unsigned __int64
0x18000f87a  mov     r8, rbx; unsigned __int16 *
0x18000f87d  mov     rcx, rax; unsigned __int16 *
0x18000f880  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f885  mov     ecx, eax
0x18000f887  jmp     short loc_18000F88E
0x18000f889  mov     ecx, 80070057h
0x18000f88e  mov     eax, ecx
0x18000f890  add     rsp, 28h
0x18000f894  pop     rdi
0x18000f895  pop     rsi
0x18000f896  pop     rbp
0x18000f897  pop     rbx
0x18000f898  retn
```
