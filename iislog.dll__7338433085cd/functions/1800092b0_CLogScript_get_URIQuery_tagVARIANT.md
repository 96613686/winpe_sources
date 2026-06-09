# CLogScript::get_URIQuery(tagVARIANT *)

- ea: `0x1800092b0`
- end: `0x18000931d`
- name: `?get_URIQuery@CLogScript@@UEAAJPEAUtagVARIANT@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(CLogScript *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002034`
- `0x1800092b0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800092c9`
- `KERNEL32!EnterCriticalSection` at `0x1800092c9`
- `KERNEL32!LeaveCriticalSection` at `0x180009305`
- `KERNEL32!LeaveCriticalSection` at `0x180009305`

## pseudocode

```c
__int64 __fastcall CLogScript::get_URIQuery(CLogScript *this, struct tagVARIANT *a2)
{
  int v4; // edx
  __int64 v5; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v5 = *((_QWORD *)this + 19);
  if ( v5 )
  {
    if ( *(_BYTE *)v5 != 45 || *(_BYTE *)(v5 + 1) )
    {
      a2->vt = 8;
      a2->llVal = (LONGLONG)A2WBSTR((LPCCH)v5, v4);
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
0x1800092b0  mov     [rsp+arg_0], rbx
0x1800092b5  mov     [rsp+arg_8], rsi
0x1800092ba  push    rdi
0x1800092bb  sub     rsp, 20h
0x1800092bf  mov     rbx, rcx
0x1800092c2  mov     rdi, rdx
0x1800092c5  add     rcx, 8; lpCriticalSection
0x1800092c9  call    cs:__imp_EnterCriticalSection
0x1800092cf  mov     rcx, [rbx+98h]; lpMultiByteStr
0x1800092d6  xor     eax, eax
0x1800092d8  test    rcx, rcx
0x1800092db  jnz     short loc_1800092E4
0x1800092dd  mov     word ptr [rdi], 1
0x1800092e2  jmp     short loc_180009301
0x1800092e4  cmp     byte ptr [rcx], 2Dh ; '-'
0x1800092e7  jnz     short loc_1800092F3
0x1800092e9  cmp     [rcx+1], al
0x1800092ec  jnz     short loc_1800092F3
0x1800092ee  mov     [rdi], ax
0x1800092f1  jmp     short loc_180009301
0x1800092f3  mov     word ptr [rdi], 8
0x1800092f8  call    ?A2WBSTR@@YAPEAGPEBDH@Z; A2WBSTR(char const *,int)
0x1800092fd  mov     [rdi+8], rax
0x180009301  lea     rcx, [rbx+8]; lpCriticalSection
0x180009305  call    cs:__imp_LeaveCriticalSection
0x18000930b  mov     rbx, [rsp+28h+arg_0]
0x180009310  xor     eax, eax
0x180009312  mov     rsi, [rsp+28h+arg_8]
0x180009317  add     rsp, 20h
0x18000931b  pop     rdi
0x18000931c  retn
```
