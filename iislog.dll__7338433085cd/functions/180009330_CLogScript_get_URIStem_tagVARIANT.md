# CLogScript::get_URIStem(tagVARIANT *)

- ea: `0x180009330`
- end: `0x18000939d`
- name: `?get_URIStem@CLogScript@@UEAAJPEAUtagVARIANT@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(CLogScript *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002034`
- `0x180009330`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180009349`
- `KERNEL32!EnterCriticalSection` at `0x180009349`
- `KERNEL32!LeaveCriticalSection` at `0x180009385`
- `KERNEL32!LeaveCriticalSection` at `0x180009385`

## pseudocode

```c
__int64 __fastcall CLogScript::get_URIStem(CLogScript *this, struct tagVARIANT *a2)
{
  int v4; // edx
  __int64 v5; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v5 = *((_QWORD *)this + 18);
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
0x180009330  mov     [rsp+arg_0], rbx
0x180009335  mov     [rsp+arg_8], rsi
0x18000933a  push    rdi
0x18000933b  sub     rsp, 20h
0x18000933f  mov     rbx, rcx
0x180009342  mov     rdi, rdx
0x180009345  add     rcx, 8; lpCriticalSection
0x180009349  call    cs:__imp_EnterCriticalSection
0x18000934f  mov     rcx, [rbx+90h]; lpMultiByteStr
0x180009356  xor     eax, eax
0x180009358  test    rcx, rcx
0x18000935b  jnz     short loc_180009364
0x18000935d  mov     word ptr [rdi], 1
0x180009362  jmp     short loc_180009381
0x180009364  cmp     byte ptr [rcx], 2Dh ; '-'
0x180009367  jnz     short loc_180009373
0x180009369  cmp     [rcx+1], al
0x18000936c  jnz     short loc_180009373
0x18000936e  mov     [rdi], ax
0x180009371  jmp     short loc_180009381
0x180009373  mov     word ptr [rdi], 8
0x180009378  call    ?A2WBSTR@@YAPEAGPEBDH@Z; A2WBSTR(char const *,int)
0x18000937d  mov     [rdi+8], rax
0x180009381  lea     rcx, [rbx+8]; lpCriticalSection
0x180009385  call    cs:__imp_LeaveCriticalSection
0x18000938b  mov     rbx, [rsp+28h+arg_0]
0x180009390  xor     eax, eax
0x180009392  mov     rsi, [rsp+28h+arg_8]
0x180009397  add     rsp, 20h
0x18000939b  pop     rdi
0x18000939c  retn
```
