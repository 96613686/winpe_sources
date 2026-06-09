# CIISWebService::NonDelegatingQueryInterface(_GUID const &,void * *)

- ea: `0x180009860`
- end: `0x180009902`
- name: `?NonDelegatingQueryInterface@CIISWebService@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `162`
- prototype: `__int64 __fastcall(CIISWebService *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180009860`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISWebService::NonDelegatingQueryInterface(
        unsigned __int64 this,
        const struct _GUID *a2,
        char **a3)
{
  char *v4; // rdx
  char *v5; // rax

  if ( !a3 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IISWebService.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IISWebService.Data4 )
  {
    v4 = (char *)(this - 32);
LABEL_13:
    *a3 = v4;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IADsExtension.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IADsExtension.Data4 )
  {
    v5 = (char *)(this - 32);
    this -= 8LL;
LABEL_12:
    v4 = (char *)(this & ((unsigned __int128)-(__int128)(unsigned __int64)v5 >> 64));
    goto LABEL_13;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    v5 = (char *)(this - 32);
    goto LABEL_12;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x180009860  sub     rsp, 28h
0x180009864  test    r8, r8
0x180009867  jnz     short loc_180009873
0x180009869  mov     eax, 80004003h
0x18000986e  jmp     loc_1800098FD
0x180009873  mov     rax, [rdx]
0x180009876  cmp     rax, qword ptr cs:IID_IISWebService.Data1
0x18000987d  jnz     short loc_180009892
0x18000987f  mov     rax, [rdx+8]
0x180009883  cmp     rax, qword ptr cs:IID_IISWebService.Data4
0x18000988a  jnz     short loc_180009892
0x18000988c  lea     rdx, [rcx-20h]
0x180009890  jmp     short loc_1800098DB
0x180009892  mov     rax, [rdx]
0x180009895  cmp     rax, qword ptr cs:IID_IADsExtension.Data1
0x18000989c  jnz     short loc_1800098B5
0x18000989e  mov     rax, [rdx+8]
0x1800098a2  cmp     rax, qword ptr cs:IID_IADsExtension.Data4
0x1800098a9  jnz     short loc_1800098B5
0x1800098ab  lea     rax, [rcx-20h]
0x1800098af  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1800098b3  jmp     short loc_1800098D2
0x1800098b5  mov     rax, [rdx]
0x1800098b8  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800098bf  jnz     short loc_1800098F1
0x1800098c1  mov     rax, [rdx+8]
0x1800098c5  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800098cc  jnz     short loc_1800098F1
0x1800098ce  lea     rax, [rcx-20h]
0x1800098d2  neg     rax
0x1800098d5  sbb     rdx, rdx
0x1800098d8  and     rdx, rcx
0x1800098db  mov     [r8], rdx
0x1800098de  mov     rcx, rdx
0x1800098e1  mov     rax, [rdx]
0x1800098e4  mov     rax, [rax+8]
0x1800098e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098ed  xor     eax, eax
0x1800098ef  jmp     short loc_1800098FD
0x1800098f1  mov     qword ptr [r8], 0
0x1800098f8  mov     eax, 80004002h
0x1800098fd  add     rsp, 28h
0x180009901  retn
```
