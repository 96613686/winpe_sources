# MidlFreeDevProperties(_DEVPROPERTY *,ulong)

- ea: `0x14001a068`
- end: `0x14001a0d8`
- name: `?MidlFreeDevProperties@@YAXPEAU_DEVPROPERTY@@K@Z`
- size: `112`
- prototype: `void __fastcall(struct _DEVPROPERTY *, unsigned int)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b7c4`
- `0x14000deb0`
- `0x14000ef44`
- `0x14000f074`
- `0x14000f83c`
- `0x14000f8bc`
- `0x14000faa8`
- `0x140019c5c`

## callees

- `0x140009090`
- `0x14001a068`

## pseudocode

```c
void __fastcall MidlFreeDevProperties(struct _DEVPROPERTY *a1, unsigned int a2)
{
  unsigned int v2; // esi
  __int64 v5; // r14
  PVOID Buffer; // rcx
  WCHAR *LocaleName; // rcx

  if ( a1 )
  {
    v2 = 0;
    if ( a2 )
    {
      v5 = 0;
      do
      {
        Buffer = a1[v5].Buffer;
        if ( Buffer )
        {
          MIDL_user_free(Buffer);
          a1[v5].Buffer = 0;
        }
        LocaleName = (WCHAR *)a1[v5].CompKey.LocaleName;
        if ( LocaleName )
        {
          MIDL_user_free(LocaleName);
          a1[v5].CompKey.LocaleName = 0;
        }
        ++v2;
        ++v5;
      }
      while ( v2 < a2 );
    }
    MIDL_user_free(a1);
  }
}

```

## disassembly

```asm
0x14001a068  test    rcx, rcx
0x14001a06b  jz      short locret_14001A0D7
0x14001a06d  push    rbx
0x14001a06e  push    rbp
0x14001a06f  push    rsi
0x14001a070  push    rdi
0x14001a071  push    r14
0x14001a073  sub     rsp, 20h
0x14001a077  xor     esi, esi
0x14001a079  mov     ebp, edx
0x14001a07b  mov     rbx, rcx
0x14001a07e  test    edx, edx
0x14001a080  jz      short loc_14001A0C5
0x14001a082  xor     r14d, r14d
0x14001a085  lea     rdi, [r14+r14*2]
0x14001a089  add     rdi, rdi
0x14001a08c  mov     rcx, [rbx+rdi*8+28h]; void *
0x14001a091  test    rcx, rcx
0x14001a094  jz      short loc_14001A0A4
0x14001a096  call    MIDL_user_free
0x14001a09b  mov     qword ptr [rbx+rdi*8+28h], 0
0x14001a0a4  mov     rcx, [rbx+rdi*8+18h]; void *
0x14001a0a9  test    rcx, rcx
0x14001a0ac  jz      short loc_14001A0BC
0x14001a0ae  call    MIDL_user_free
0x14001a0b3  mov     qword ptr [rbx+rdi*8+18h], 0
0x14001a0bc  inc     esi
0x14001a0be  inc     r14
0x14001a0c1  cmp     esi, ebp
0x14001a0c3  jb      short loc_14001A085
0x14001a0c5  mov     rcx, rbx; void *
0x14001a0c8  call    MIDL_user_free
0x14001a0cd  add     rsp, 20h
0x14001a0d1  pop     r14
0x14001a0d3  pop     rdi
0x14001a0d4  pop     rsi
0x14001a0d5  pop     rbp
0x14001a0d6  pop     rbx
0x14001a0d7  retn
```
