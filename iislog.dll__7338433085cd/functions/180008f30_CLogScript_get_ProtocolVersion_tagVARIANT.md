# CLogScript::get_ProtocolVersion(tagVARIANT *)

- ea: `0x180008f30`
- end: `0x180008f9d`
- name: `?get_ProtocolVersion@CLogScript@@UEAAJPEAUtagVARIANT@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(CLogScript *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002034`
- `0x180008f30`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180008f49`
- `KERNEL32!EnterCriticalSection` at `0x180008f49`
- `KERNEL32!LeaveCriticalSection` at `0x180008f85`
- `KERNEL32!LeaveCriticalSection` at `0x180008f85`

## pseudocode

```c
__int64 __fastcall CLogScript::get_ProtocolVersion(CLogScript *this, struct tagVARIANT *a2)
{
  int v4; // edx
  __int64 v5; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v5 = *((_QWORD *)this + 20);
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
0x180008f30  mov     [rsp+arg_0], rbx
0x180008f35  mov     [rsp+arg_8], rsi
0x180008f3a  push    rdi
0x180008f3b  sub     rsp, 20h
0x180008f3f  mov     rbx, rcx
0x180008f42  mov     rdi, rdx
0x180008f45  add     rcx, 8; lpCriticalSection
0x180008f49  call    cs:__imp_EnterCriticalSection
0x180008f4f  mov     rcx, [rbx+0A0h]; lpMultiByteStr
0x180008f56  xor     eax, eax
0x180008f58  test    rcx, rcx
0x180008f5b  jnz     short loc_180008F64
0x180008f5d  mov     word ptr [rdi], 1
0x180008f62  jmp     short loc_180008F81
0x180008f64  cmp     byte ptr [rcx], 2Dh ; '-'
0x180008f67  jnz     short loc_180008F73
0x180008f69  cmp     [rcx+1], al
0x180008f6c  jnz     short loc_180008F73
0x180008f6e  mov     [rdi], ax
0x180008f71  jmp     short loc_180008F81
0x180008f73  mov     word ptr [rdi], 8
0x180008f78  call    ?A2WBSTR@@YAPEAGPEBDH@Z; A2WBSTR(char const *,int)
0x180008f7d  mov     [rdi+8], rax
0x180008f81  lea     rcx, [rbx+8]; lpCriticalSection
0x180008f85  call    cs:__imp_LeaveCriticalSection
0x180008f8b  mov     rbx, [rsp+28h+arg_0]
0x180008f90  xor     eax, eax
0x180008f92  mov     rsi, [rsp+28h+arg_8]
0x180008f97  add     rsp, 20h
0x180008f9b  pop     rdi
0x180008f9c  retn
```
