# CLogScript::get_ServiceName(tagVARIANT *)

- ea: `0x1800091b0`
- end: `0x18000921d`
- name: `?get_ServiceName@CLogScript@@UEAAJPEAUtagVARIANT@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(CLogScript *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180002034`
- `0x1800091b0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800091c9`
- `KERNEL32!EnterCriticalSection` at `0x1800091c9`
- `KERNEL32!LeaveCriticalSection` at `0x180009205`
- `KERNEL32!LeaveCriticalSection` at `0x180009205`

## pseudocode

```c
__int64 __fastcall CLogScript::get_ServiceName(CLogScript *this, struct tagVARIANT *a2)
{
  int v4; // edx
  __int64 v5; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v5 = *((_QWORD *)this + 29);
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
0x1800091b0  mov     [rsp+arg_0], rbx
0x1800091b5  mov     [rsp+arg_8], rsi
0x1800091ba  push    rdi
0x1800091bb  sub     rsp, 20h
0x1800091bf  mov     rbx, rcx
0x1800091c2  mov     rdi, rdx
0x1800091c5  add     rcx, 8; lpCriticalSection
0x1800091c9  call    cs:__imp_EnterCriticalSection
0x1800091cf  mov     rcx, [rbx+0E8h]; lpMultiByteStr
0x1800091d6  xor     eax, eax
0x1800091d8  test    rcx, rcx
0x1800091db  jnz     short loc_1800091E4
0x1800091dd  mov     word ptr [rdi], 1
0x1800091e2  jmp     short loc_180009201
0x1800091e4  cmp     byte ptr [rcx], 2Dh ; '-'
0x1800091e7  jnz     short loc_1800091F3
0x1800091e9  cmp     [rcx+1], al
0x1800091ec  jnz     short loc_1800091F3
0x1800091ee  mov     [rdi], ax
0x1800091f1  jmp     short loc_180009201
0x1800091f3  mov     word ptr [rdi], 8
0x1800091f8  call    ?A2WBSTR@@YAPEAGPEBDH@Z; A2WBSTR(char const *,int)
0x1800091fd  mov     [rdi+8], rax
0x180009201  lea     rcx, [rbx+8]; lpCriticalSection
0x180009205  call    cs:__imp_LeaveCriticalSection
0x18000920b  mov     rbx, [rsp+28h+arg_0]
0x180009210  xor     eax, eax
0x180009212  mov     rsi, [rsp+28h+arg_8]
0x180009217  add     rsp, 20h
0x18000921b  pop     rdi
0x18000921c  retn
```
