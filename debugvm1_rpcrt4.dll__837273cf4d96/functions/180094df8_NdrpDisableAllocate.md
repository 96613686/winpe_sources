# NdrpDisableAllocate

- ea: `0x180094df8`
- end: `0x180094ea2`
- name: `NdrpDisableAllocate`
- size: `170`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18001dd40`
- `0x180094dc0`
- `0x1800c2e30`
- `0x1800c2fc0`
- `0x1800cdaa0`

## callees

- `0x180022870`
- `0x180094df8`
- `0x1800a37e4`
- `0x1800c2bc8`
- `0x1800c2c88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180094e31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180094e77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180094e31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180094e77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180094e1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180094e1d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180094e84`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180094e84`

## pseudocode

```c
void __fastcall NdrpDisableAllocate(int a1)
{
  struct _ALLOCATION_CONTEXT *AllocContext; // rax
  struct _ALLOCATION_CONTEXT *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  int v5; // edx
  int v6; // esi

  AllocContext = GetAllocContext();
  v3 = AllocContext;
  if ( AllocContext )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)AllocContext + 24);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)AllocContext + 24));
    if ( a1 )
    {
      if ( !*((_QWORD *)v3 + 9) )
      {
        LeaveCriticalSection(v4);
        return;
      }
      v5 = *(_DWORD *)(*((_QWORD *)v3 + 10) + 4LL * (unsigned int)--*((_DWORD *)v3 + 23));
    }
    else
    {
      v5 = *((_DWORD *)v3 + 4) - 1;
    }
    v6 = 0;
    if ( *((_DWORD *)v3 + 4) )
    {
      *((_DWORD *)v3 + 4) = v5;
      if ( v5 )
      {
LABEL_12:
        LeaveCriticalSection(v4);
        if ( v6 )
        {
          DeleteCriticalSection(v4);
          FreeWrapper(v3);
        }
        return;
      }
      NdrpReleaseMemory(v3);
    }
    if ( !*((_DWORD *)v3 + 16) )
    {
      v6 = 1;
      SetAllocContext(0);
    }
    goto LABEL_12;
  }
}

```

## disassembly

```asm
0x180094df8  mov     [rsp+arg_0], rbx
0x180094dfd  mov     [rsp+arg_8], rsi
0x180094e02  push    rdi
0x180094e03  sub     rsp, 20h
0x180094e07  mov     esi, ecx
0x180094e09  call    ?GetAllocContext@@YAPEAU_ALLOCATION_CONTEXT@@XZ; GetAllocContext(void)
0x180094e0e  mov     rbx, rax
0x180094e11  test    rax, rax
0x180094e14  jz      short loc_180094E92
0x180094e16  lea     rdi, [rax+18h]
0x180094e1a  mov     rcx, rdi; lpCriticalSection
0x180094e1d  call    cs:__imp_EnterCriticalSection
0x180094e23  test    esi, esi
0x180094e25  jz      short loc_180094E48
0x180094e27  cmp     qword ptr [rbx+48h], 0
0x180094e2c  jnz     short loc_180094E39
0x180094e2e  mov     rcx, rdi; lpCriticalSection
0x180094e31  call    cs:__imp_LeaveCriticalSection
0x180094e37  jmp     short loc_180094E92
0x180094e39  dec     dword ptr [rbx+5Ch]
0x180094e3c  mov     ecx, [rbx+5Ch]
0x180094e3f  mov     rax, [rbx+50h]
0x180094e43  mov     edx, [rax+rcx*4]
0x180094e46  jmp     short loc_180094E4D
0x180094e48  mov     edx, [rbx+10h]
0x180094e4b  dec     edx
0x180094e4d  xor     esi, esi
0x180094e4f  cmp     [rbx+10h], esi
0x180094e52  jz      short loc_180094E63
0x180094e54  mov     [rbx+10h], edx
0x180094e57  test    edx, edx
0x180094e59  jnz     short loc_180094E74
0x180094e5b  mov     rcx, rbx
0x180094e5e  call    NdrpReleaseMemory
0x180094e63  cmp     [rbx+40h], esi
0x180094e66  jnz     short loc_180094E74
0x180094e68  xor     ecx, ecx; lpTlsValue
0x180094e6a  mov     esi, 1
0x180094e6f  call    ?SetAllocContext@@YAXPEAU_ALLOCATION_CONTEXT@@@Z; SetAllocContext(_ALLOCATION_CONTEXT *)
0x180094e74  mov     rcx, rdi; lpCriticalSection
0x180094e77  call    cs:__imp_LeaveCriticalSection
0x180094e7d  test    esi, esi
0x180094e7f  jz      short loc_180094E92
0x180094e81  mov     rcx, rdi; lpCriticalSection
0x180094e84  call    cs:__imp_DeleteCriticalSection
0x180094e8a  mov     rcx, rbx; lpMem
0x180094e8d  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180094e92  mov     rbx, [rsp+28h+arg_0]
0x180094e97  mov     rsi, [rsp+28h+arg_8]
0x180094e9c  add     rsp, 20h
0x180094ea0  pop     rdi
0x180094ea1  retn
```
