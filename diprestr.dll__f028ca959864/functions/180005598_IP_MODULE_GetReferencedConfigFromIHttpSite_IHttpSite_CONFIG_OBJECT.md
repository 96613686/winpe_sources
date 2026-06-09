# IP_MODULE::GetReferencedConfigFromIHttpSite(IHttpSite *,CONFIG_OBJECT * *)

- ea: `0x180005598`
- end: `0x1800055e9`
- name: `?GetReferencedConfigFromIHttpSite@IP_MODULE@@CAJPEAVIHttpSite@@PEAPEAVCONFIG_OBJECT@@@Z`
- size: `81`
- prototype: `__int64 __fastcall(struct IHttpSite *, struct CONFIG_OBJECT **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800055f0`
- `0x1800061c0`

## callees

- `0x180005598`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall IP_MODULE::GetReferencedConfigFromIHttpSite(struct IHttpSite *a1, struct CONFIG_OBJECT **a2)
{
  __int64 v2; // rax
  __int64 (__fastcall ***v4)(_QWORD, void *); // rax
  volatile signed __int32 *v5; // rax
  unsigned int v6; // ecx

  v2 = *(_QWORD *)a1;
  *a2 = 0;
  v4 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpSite *))(v2 + 16))(a1);
  v5 = (volatile signed __int32 *)(**v4)(v4, g_pModuleID);
  if ( v5 )
  {
    v6 = 0;
    _InterlockedIncrement(v5 + 4);
    *a2 = (struct CONFIG_OBJECT *)v5;
  }
  else
  {
    return (unsigned int)-2147024894;
  }
  return v6;
}

```

## disassembly

```asm
0x180005598  push    rbx
0x18000559a  sub     rsp, 20h
0x18000559e  mov     rax, [rcx]
0x1800055a1  mov     rbx, rdx
0x1800055a4  mov     qword ptr [rdx], 0
0x1800055ab  mov     rax, [rax+10h]
0x1800055af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055b4  mov     rdx, cs:?g_pModuleID@@3PEAXEA; void * g_pModuleID
0x1800055bb  mov     r8, rax
0x1800055be  mov     rcx, [rax]
0x1800055c1  mov     rax, [rcx]
0x1800055c4  mov     rcx, r8
0x1800055c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055cc  test    rax, rax
0x1800055cf  jnz     short loc_1800055D8
0x1800055d1  mov     ecx, 80070002h
0x1800055d6  jmp     short loc_1800055E1
0x1800055d8  xor     ecx, ecx
0x1800055da  lock inc dword ptr [rax+10h]
0x1800055de  mov     [rbx], rax
0x1800055e1  mov     eax, ecx
0x1800055e3  add     rsp, 20h
0x1800055e7  pop     rbx
0x1800055e8  retn
```
