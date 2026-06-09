# CLogScript::get_ProtocolStatus(tagVARIANT *)

- ea: `0x180008eb0`
- end: `0x180008f1d`
- name: `?get_ProtocolStatus@CLogScript@@UEAAJPEAUtagVARIANT@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(CLogScript *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008eb0`

## import_xrefs

- `msvcrt!atol` at `0x180008ef8`
- `msvcrt!atol` at `0x180008ef8`
- `KERNEL32!EnterCriticalSection` at `0x180008ec9`
- `KERNEL32!EnterCriticalSection` at `0x180008ec9`
- `KERNEL32!LeaveCriticalSection` at `0x180008f05`
- `KERNEL32!LeaveCriticalSection` at `0x180008f05`

## pseudocode

```c
__int64 __fastcall CLogScript::get_ProtocolStatus(CLogScript *this, struct tagVARIANT *a2)
{
  __int64 v4; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v4 = *((_QWORD *)this + 26);
  if ( v4 )
  {
    if ( *(_BYTE *)v4 != 45 || *(_BYTE *)(v4 + 1) )
    {
      a2->vt = 3;
      a2->lVal = atol((const char *)v4);
    }
    else
    {
      a2->vt = 0;
    }
  }
  else
  {
    a2->vt = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return 0;
}

```

## disassembly

```asm
0x180008eb0  mov     [rsp+arg_0], rbx
0x180008eb5  mov     [rsp+arg_8], rsi
0x180008eba  push    rdi
0x180008ebb  sub     rsp, 20h
0x180008ebf  mov     rbx, rcx
0x180008ec2  mov     rdi, rdx
0x180008ec5  add     rcx, 8; lpCriticalSection
0x180008ec9  call    cs:__imp_EnterCriticalSection
0x180008ecf  mov     rcx, [rbx+0D0h]; String
0x180008ed6  xor     eax, eax
0x180008ed8  test    rcx, rcx
0x180008edb  jnz     short loc_180008EE4
0x180008edd  mov     word ptr [rdi], 1
0x180008ee2  jmp     short loc_180008F01
0x180008ee4  cmp     byte ptr [rcx], 2Dh ; '-'
0x180008ee7  jnz     short loc_180008EF3
0x180008ee9  cmp     [rcx+1], al
0x180008eec  jnz     short loc_180008EF3
0x180008eee  mov     [rdi], ax
0x180008ef1  jmp     short loc_180008F01
0x180008ef3  mov     word ptr [rdi], 3
0x180008ef8  call    cs:__imp_atol
0x180008efe  mov     [rdi+8], eax
0x180008f01  lea     rcx, [rbx+8]; lpCriticalSection
0x180008f05  call    cs:__imp_LeaveCriticalSection
0x180008f0b  mov     rbx, [rsp+28h+arg_0]
0x180008f10  xor     eax, eax
0x180008f12  mov     rsi, [rsp+28h+arg_8]
0x180008f17  add     rsp, 20h
0x180008f1b  pop     rdi
0x180008f1c  retn
```
