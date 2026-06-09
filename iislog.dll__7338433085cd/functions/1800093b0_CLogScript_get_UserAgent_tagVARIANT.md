# CLogScript::get_UserAgent(tagVARIANT *)

- ea: `0x1800093b0`
- end: `0x18000941d`
- name: `?get_UserAgent@CLogScript@@UEAAJPEAUtagVARIANT@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(CLogScript *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180002034`
- `0x1800093b0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800093c9`
- `KERNEL32!EnterCriticalSection` at `0x1800093c9`
- `KERNEL32!LeaveCriticalSection` at `0x180009405`
- `KERNEL32!LeaveCriticalSection` at `0x180009405`

## pseudocode

```c
__int64 __fastcall CLogScript::get_UserAgent(CLogScript *this, struct tagVARIANT *a2)
{
  int v4; // edx
  __int64 v5; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v5 = *((_QWORD *)this + 31);
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
0x1800093b0  mov     [rsp+arg_0], rbx
0x1800093b5  mov     [rsp+arg_8], rsi
0x1800093ba  push    rdi
0x1800093bb  sub     rsp, 20h
0x1800093bf  mov     rbx, rcx
0x1800093c2  mov     rdi, rdx
0x1800093c5  add     rcx, 8; lpCriticalSection
0x1800093c9  call    cs:__imp_EnterCriticalSection
0x1800093cf  mov     rcx, [rbx+0F8h]; lpMultiByteStr
0x1800093d6  xor     eax, eax
0x1800093d8  test    rcx, rcx
0x1800093db  jnz     short loc_1800093E4
0x1800093dd  mov     word ptr [rdi], 1
0x1800093e2  jmp     short loc_180009401
0x1800093e4  cmp     byte ptr [rcx], 2Dh ; '-'
0x1800093e7  jnz     short loc_1800093F3
0x1800093e9  cmp     [rcx+1], al
0x1800093ec  jnz     short loc_1800093F3
0x1800093ee  mov     [rdi], ax
0x1800093f1  jmp     short loc_180009401
0x1800093f3  mov     word ptr [rdi], 8
0x1800093f8  call    ?A2WBSTR@@YAPEAGPEBDH@Z; A2WBSTR(char const *,int)
0x1800093fd  mov     [rdi+8], rax
0x180009401  lea     rcx, [rbx+8]; lpCriticalSection
0x180009405  call    cs:__imp_LeaveCriticalSection
0x18000940b  mov     rbx, [rsp+28h+arg_0]
0x180009410  xor     eax, eax
0x180009412  mov     rsi, [rsp+28h+arg_8]
0x180009417  add     rsp, 20h
0x18000941b  pop     rdi
0x18000941c  retn
```
