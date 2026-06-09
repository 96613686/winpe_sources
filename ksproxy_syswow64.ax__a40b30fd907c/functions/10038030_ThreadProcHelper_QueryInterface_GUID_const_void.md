# ThreadProcHelper::QueryInterface(_GUID const &,void * *)

- ea: `0x10038030`
- end: `0x100380b1`
- name: `?QueryInterface@ThreadProcHelper@@UAGJABU_GUID@@PAPAX@Z`
- size: `129`
- prototype: `int(ThreadProcHelper *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x100075ad`
- `0x1002d510`
- `0x10038030`

## string_xrefs

- `0x10038049`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`

## pseudocode

```c
int __stdcall ThreadProcHelper::QueryInterface(ThreadProcHelper *this, const struct _GUID *a2, void **a3)
{
  int v3; // edi
  int v5; // ecx
  int v6; // ecx
  unsigned int v7; // [esp+0h] [ebp-8h]
  const char *v8; // [esp+4h] [ebp-4h]
  int savedregs; // [esp+8h] [ebp+0h]
  int retaddr; // [esp+Ch] [ebp+4h]

  v3 = 0;
  if ( a3 )
  {
    v5 = 0;
    *a3 = 0;
    while ( *(&a2->Data1 + v5) == *(&_GUID_0beaa6cc_1392_4e3c_b0df_51b861bd6c6e.Data1 + v5) )
    {
      if ( ++v5 == 4 )
      {
LABEL_10:
        *a3 = this;
        (*(void (__thiscall **)(_DWORD, ThreadProcHelper *))(*(_DWORD *)this + 4))(
          *(_DWORD *)(*(_DWORD *)this + 4),
          this);
        return v3;
      }
    }
    v6 = 0;
    while ( *(&a2->Data1 + v6) == *(&_GUID_00000000_0000_0000_c000_000000000046.Data1 + v6) )
    {
      if ( ++v6 == 4 )
        goto LABEL_10;
    }
    return -2147467262;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
      (void *)0x80004003,
      v7,
      v8,
      savedregs);
    return -2147467261;
  }
}

```

## disassembly

```asm
0x10038030  mov     edi, edi
0x10038032  push    ebp; int
0x10038033  mov     ebp, esp
0x10038035  mov     edx, [ebp+arg_8]
0x10038038  push    esi; char *
0x10038039  push    edi; unsigned int
0x1003803a  xor     edi, edi
0x1003803c  test    edx, edx
0x1003803e  jnz     short loc_1003805A
0x10038040  mov     ecx, [ebp+4]
0x10038043  mov     esi, 80004003h
0x10038048  push    esi; void *
0x10038049  push    offset aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1003804e  push    3Dh ; '='
0x10038050  pop     edx
0x10038051  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x10038056  mov     eax, esi
0x10038058  jmp     short loc_100380AB
0x1003805a  mov     esi, [ebp+arg_4]
0x1003805d  xor     ecx, ecx
0x1003805f  push    ebx
0x10038060  mov     [edx], edi
0x10038062  mov     ebx, offset __GUID_0beaa6cc_1392_4e3c_b0df_51b861bd6c6e
0x10038067  mov     eax, [esi+ecx*4]
0x1003806a  cmp     eax, [ebx+ecx*4]
0x1003806d  jnz     short loc_10038077
0x1003806f  inc     ecx
0x10038070  cmp     ecx, 4
0x10038073  jnz     short loc_10038067
0x10038075  jmp     short loc_1003808C
0x10038077  mov     ebx, offset __GUID_00000000_0000_0000_c000_000000000046
0x1003807c  xor     ecx, ecx
0x1003807e  mov     eax, [esi+ecx*4]
0x10038081  cmp     eax, [ebx+ecx*4]
0x10038084  jnz     short loc_100380A3
0x10038086  inc     ecx
0x10038087  cmp     ecx, 4
0x1003808a  jnz     short loc_1003807E
0x1003808c  mov     ecx, [ebp+this]
0x1003808f  mov     [edx], ecx
0x10038091  push    ecx
0x10038092  mov     eax, [ecx]
0x10038094  mov     esi, [eax+4]
0x10038097  mov     ecx, esi; this
0x10038099  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003809f  call    esi
0x100380a1  jmp     short loc_100380A8
0x100380a3  mov     edi, 80004002h
0x100380a8  mov     eax, edi
0x100380aa  pop     ebx
0x100380ab  pop     edi
0x100380ac  pop     esi
0x100380ad  pop     ebp
0x100380ae  retn    0Ch
```
