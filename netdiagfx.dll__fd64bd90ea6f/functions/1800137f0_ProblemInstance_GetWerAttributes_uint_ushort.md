# ProblemInstance::GetWerAttributes(uint *,ushort * *)

- ea: `0x1800137f0`
- end: `0x180013930`
- name: `?GetWerAttributes@ProblemInstance@@QEAAJPEAIPEAPEAG@Z`
- size: `320`
- prototype: `__int64 __fastcall(ProblemInstance *__hidden this, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001bfc0`

## callees

- `0x1800137f0`
- `0x18002c80e`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800138b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800138c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800138d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001390b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800138b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800138c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800138d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001390b`

## pseudocode

```c
__int64 __fastcall ProblemInstance::GetWerAttributes(ProblemInstance *this, unsigned int *a2, unsigned __int16 **a3)
{
  int v5; // r13d
  const wchar_t **v6; // rbx
  void *v7; // r15
  unsigned int v8; // r14d
  char *v9; // rdi
  _DWORD *v10; // rax
  unsigned int v12; // [rsp+68h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+58h] BYREF

  v12 = 0;
  pv = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  *a2 = 0;
  *a3 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, LPVOID *))(**((_QWORD **)this + 9) + 120LL))(
         *((_QWORD *)this + 9),
         &v12,
         &pv);
  if ( v5 >= 0 )
  {
    v6 = (const wchar_t **)pv;
    if ( pv )
    {
      v7 = pv;
      v8 = 0;
      if ( v12 )
      {
        v9 = (char *)pv;
        do
        {
          if ( *((_DWORD *)v9 + 2) == 7 )
          {
            if ( !wcscmp_0(*v6, L"werparameter") )
              *a2 = *((_DWORD *)v9 + 4);
          }
          else if ( *((_DWORD *)v9 + 2) == 10 )
          {
            if ( !wcscmp_0(*v6, L"werfile") )
            {
              *a3 = (unsigned __int16 *)*((_QWORD *)v9 + 2);
            }
            else
            {
              CoTaskMemFree(*((LPVOID *)v9 + 2));
              v6 = (const wchar_t **)pv;
            }
          }
          CoTaskMemFree((LPVOID)*v6);
          v10 = pv;
          if ( *((_DWORD *)pv + 2) == 14 )
          {
            CoTaskMemFree(*((LPVOID *)pv + 3));
            v10 = pv;
          }
          v10[2] = 0;
          ++v8;
          v6 = (const wchar_t **)((char *)pv + 144);
          v9 = (char *)pv + 144;
          pv = (char *)pv + 144;
        }
        while ( v8 < v12 );
      }
      CoTaskMemFree(v7);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800137f0  mov     [rsp-38h+arg_0], rbx
0x1800137f5  push    rbp
0x1800137f6  push    rsi
0x1800137f7  push    rdi
0x1800137f8  push    r12
0x1800137fa  push    r13
0x1800137fc  push    r14
0x1800137fe  push    r15
0x180013800  mov     rbp, rsp
0x180013803  sub     rsp, 20h
0x180013807  xor     edi, edi
0x180013809  mov     rsi, r8
0x18001380c  mov     [rbp+arg_8], edi
0x18001380f  mov     r12, rdx
0x180013812  mov     [rbp+pv], rdi
0x180013816  test    rdx, rdx
0x180013819  jz      loc_180013916
0x18001381f  test    r8, r8
0x180013822  jz      loc_180013916
0x180013828  mov     [rdx], edi
0x18001382a  lea     rdx, [rbp+arg_8]
0x18001382e  mov     [r8], rdi
0x180013831  lea     r8, [rbp+pv]
0x180013835  mov     rcx, [rcx+48h]
0x180013839  mov     rax, [rcx]
0x18001383c  mov     rax, [rax+78h]
0x180013840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013845  mov     r13d, eax
0x180013848  test    eax, eax
0x18001384a  js      loc_180013911
0x180013850  mov     rbx, [rbp+pv]
0x180013854  test    rbx, rbx
0x180013857  jz      loc_180013911
0x18001385d  mov     r15, rbx
0x180013860  mov     r14d, edi
0x180013863  cmp     [rbp+arg_8], edi
0x180013866  jbe     loc_180013908
0x18001386c  mov     rdi, rbx
0x18001386f  cmp     dword ptr [rdi+8], 7
0x180013873  jnz     short loc_180013891
0x180013875  mov     rcx, [rbx]; String1
0x180013878  lea     rdx, aWerparameter; "werparameter"
0x18001387f  call    wcscmp_0
0x180013884  test    eax, eax
0x180013886  jnz     short loc_1800138C1
0x180013888  mov     eax, [rdi+10h]
0x18001388b  mov     [r12], eax
0x18001388f  jmp     short loc_1800138C1
0x180013891  cmp     dword ptr [rdi+8], 0Ah
0x180013895  jnz     short loc_1800138C1
0x180013897  mov     rcx, [rbx]; String1
0x18001389a  lea     rdx, aWerfile; "werfile"
0x1800138a1  call    wcscmp_0
0x1800138a6  test    eax, eax
0x1800138a8  jnz     short loc_1800138B3
0x1800138aa  mov     rax, [rdi+10h]
0x1800138ae  mov     [rsi], rax
0x1800138b1  jmp     short loc_1800138C1
0x1800138b3  mov     rcx, [rdi+10h]; pv
0x1800138b7  call    cs:__imp_CoTaskMemFree
0x1800138bd  mov     rbx, [rbp+pv]
0x1800138c1  mov     rcx, [rbx]; pv
0x1800138c4  call    cs:__imp_CoTaskMemFree
0x1800138ca  mov     rax, [rbp+pv]
0x1800138ce  cmp     dword ptr [rax+8], 0Eh
0x1800138d2  jnz     short loc_1800138E2
0x1800138d4  mov     rcx, [rax+18h]; pv
0x1800138d8  call    cs:__imp_CoTaskMemFree
0x1800138de  mov     rax, [rbp+pv]
0x1800138e2  mov     dword ptr [rax+8], 0
0x1800138e9  inc     r14d
0x1800138ec  mov     rbx, [rbp+pv]
0x1800138f0  add     rbx, 90h
0x1800138f7  mov     rdi, rbx
0x1800138fa  mov     [rbp+pv], rbx
0x1800138fe  cmp     r14d, [rbp+arg_8]
0x180013902  jb      loc_18001386F
0x180013908  mov     rcx, r15; pv
0x18001390b  call    cs:__imp_CoTaskMemFree
0x180013911  mov     eax, r13d
0x180013914  jmp     short loc_18001391B
0x180013916  mov     eax, 80070057h
0x18001391b  mov     rbx, [rsp+20h+arg_0]
0x180013920  add     rsp, 20h
0x180013924  pop     r15
0x180013926  pop     r14
0x180013928  pop     r13
0x18001392a  pop     r12
0x18001392c  pop     rdi
0x18001392d  pop     rsi
0x18001392e  pop     rbp
0x18001392f  retn
```
