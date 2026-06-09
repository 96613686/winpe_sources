# CIISComputer::NonDelegatingQueryInterface(_GUID const &,void * *)

- ea: `0x180006de0`
- end: `0x180006e9b`
- name: `?NonDelegatingQueryInterface@CIISComputer@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int64 this, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006de0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::NonDelegatingQueryInterface(unsigned __int64 this, const struct _GUID *a2, char **a3)
{
  char *v4; // rdx
  char *v5; // rax

  if ( !a3 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IISComputer.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IISComputer.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IISComputer2.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IISComputer2.Data4 )
  {
    v4 = (char *)(this - 32);
LABEL_15:
    *a3 = v4;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IADsExtension.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IADsExtension.Data4 )
  {
    v5 = (char *)(this - 32);
    this -= 8LL;
LABEL_14:
    v4 = (char *)(this & ((unsigned __int128)-(__int128)(unsigned __int64)v5 >> 64));
    goto LABEL_15;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    v5 = (char *)(this - 32);
    goto LABEL_14;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x180006de0  sub     rsp, 28h
0x180006de4  test    r8, r8
0x180006de7  jnz     short loc_180006DF3
0x180006de9  mov     eax, 80004003h
0x180006dee  jmp     loc_180006E96
0x180006df3  mov     rax, [rdx]
0x180006df6  cmp     rax, qword ptr cs:IID_IISComputer.Data1
0x180006dfd  jnz     short loc_180006E0C
0x180006dff  mov     rax, [rdx+8]
0x180006e03  cmp     rax, qword ptr cs:IID_IISComputer.Data4
0x180006e0a  jz      short loc_180006E25
0x180006e0c  mov     rax, [rdx]
0x180006e0f  cmp     rax, qword ptr cs:IID_IISComputer2.Data1
0x180006e16  jnz     short loc_180006E2B
0x180006e18  mov     rax, [rdx+8]
0x180006e1c  cmp     rax, qword ptr cs:IID_IISComputer2.Data4
0x180006e23  jnz     short loc_180006E2B
0x180006e25  lea     rdx, [rcx-20h]
0x180006e29  jmp     short loc_180006E74
0x180006e2b  mov     rax, [rdx]
0x180006e2e  cmp     rax, qword ptr cs:IID_IADsExtension.Data1
0x180006e35  jnz     short loc_180006E4E
0x180006e37  mov     rax, [rdx+8]
0x180006e3b  cmp     rax, qword ptr cs:IID_IADsExtension.Data4
0x180006e42  jnz     short loc_180006E4E
0x180006e44  lea     rax, [rcx-20h]
0x180006e48  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180006e4c  jmp     short loc_180006E6B
0x180006e4e  mov     rax, [rdx]
0x180006e51  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180006e58  jnz     short loc_180006E8A
0x180006e5a  mov     rax, [rdx+8]
0x180006e5e  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180006e65  jnz     short loc_180006E8A
0x180006e67  lea     rax, [rcx-20h]
0x180006e6b  neg     rax
0x180006e6e  sbb     rdx, rdx
0x180006e71  and     rdx, rcx
0x180006e74  mov     [r8], rdx
0x180006e77  mov     rcx, rdx
0x180006e7a  mov     rax, [rdx]
0x180006e7d  mov     rax, [rax+8]
0x180006e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e86  xor     eax, eax
0x180006e88  jmp     short loc_180006E96
0x180006e8a  mov     qword ptr [r8], 0
0x180006e91  mov     eax, 80004002h
0x180006e96  add     rsp, 28h
0x180006e9a  retn
```
