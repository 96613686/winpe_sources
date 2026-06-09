# IStreamToBuffer(IStream *,uchar * *,int *)

- ea: `0x180019900`
- end: `0x180019a43`
- name: `?IStreamToBuffer@@YAJPEAUIStream@@PEAPEAEPEAH@Z`
- size: `323`
- prototype: `__int64 __fastcall(struct IStream *, LPVOID *, int *)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019b60`
- `0x180019db0`
- `0x180019eb0`
- `0x180019ff0`
- `0x18001a150`

## callees

- `0x18000f970`
- `0x1800103e8`
- `0x180019900`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001999f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001999f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019984`

## pseudocode

```c
__int64 __fastcall IStreamToBuffer(struct IStream *a1, LPVOID *a2, int *a3)
{
  int v6; // edi
  int v7; // esi
  unsigned __int8 *v8; // rax
  struct IStreamVtbl *lpVtbl; // rax
  char *v11; // rbp
  unsigned int v12; // r15d
  __int64 v13; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v14[16]; // [rsp+40h] [rbp-98h] BYREF
  SIZE_T cb; // [rsp+50h] [rbp-88h]

  if ( !a2 || !a3 )
    return 2147942487LL;
  *a2 = 0;
  *a3 = 0;
  memset_0(v14, 0, 0x50u);
  v6 = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, __int64))a1->lpVtbl->Stat)(a1, v14, 1);
  if ( v6 >= 0 )
  {
    v7 = cb;
    v8 = (unsigned __int8 *)CoTaskMemAlloc((unsigned int)cb);
    *a2 = v8;
    if ( v8 )
    {
      lpVtbl = a1->lpVtbl;
      v13 = 0;
      v6 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))lpVtbl->Seek)(a1, 0, 0, 0);
      if ( v6 >= 0 )
      {
        v11 = (char *)*a2;
        v12 = v7;
        LODWORD(v13) = 0;
        while ( 1 )
        {
          v6 = ((__int64 (__fastcall *)(struct IStream *, char *, _QWORD, __int64 *))a1->lpVtbl->Read)(
                 a1,
                 v11,
                 v12,
                 &v13);
          if ( v6 < 0 )
            break;
          v11 += (unsigned int)v13;
          v12 -= v13;
          if ( !(_DWORD)v13 )
          {
            *a3 = v7;
            return (unsigned int)v6;
          }
        }
      }
    }
    else
    {
      v6 = -2147024882;
    }
  }
  if ( *a2 )
  {
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180019900  push    rbx
0x180019902  push    rbp
0x180019903  push    rsi
0x180019904  push    rdi
0x180019905  push    r12
0x180019907  push    r14
0x180019909  push    r15
0x18001990b  sub     rsp, 0A0h
0x180019912  mov     rax, cs:__security_cookie
0x180019919  xor     rax, rsp
0x18001991c  mov     [rsp+0D8h+var_48], rax
0x180019924  mov     r14, r8
0x180019927  mov     rbx, rdx
0x18001992a  mov     r12, rcx
0x18001992d  test    rdx, rdx
0x180019930  jz      loc_180019A1C
0x180019936  test    r8, r8
0x180019939  jz      loc_180019A1C
0x18001993f  mov     qword ptr [rdx], 0
0x180019946  lea     rcx, [rsp+0D8h+var_98]; void *
0x18001994b  xor     edx, edx; Val
0x18001994d  mov     dword ptr [r8], 0
0x180019954  lea     r8d, [rdx+50h]; Size
0x180019958  call    memset_0
0x18001995d  mov     rax, [r12]
0x180019961  lea     rdx, [rsp+0D8h+var_98]
0x180019966  mov     r8d, 1
0x18001996c  mov     rcx, r12
0x18001996f  mov     rax, [rax+60h]
0x180019973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019978  mov     edi, eax
0x18001997a  test    eax, eax
0x18001997c  js      short loc_180019997
0x18001997e  mov     esi, dword ptr [rsp+0D8h+cb]
0x180019982  mov     ecx, esi; cb
0x180019984  call    cs:__imp_CoTaskMemAlloc
0x18001998a  mov     [rbx], rax
0x18001998d  test    rax, rax
0x180019990  jnz     short loc_1800199B0
0x180019992  mov     edi, 8007000Eh
0x180019997  mov     rcx, [rbx]; pv
0x18001999a  test    rcx, rcx
0x18001999d  jz      short loc_1800199AC
0x18001999f  call    cs:__imp_CoTaskMemFree
0x1800199a5  mov     qword ptr [rbx], 0
0x1800199ac  mov     eax, edi
0x1800199ae  jmp     short loc_180019A21
0x1800199b0  mov     rax, [r12]
0x1800199b4  xor     r9d, r9d
0x1800199b7  mov     [rsp+0D8h+var_A8], 0
0x1800199c0  xor     r8d, r8d
0x1800199c3  mov     rdx, [rsp+0D8h+var_A8]
0x1800199c8  mov     rcx, r12
0x1800199cb  mov     rax, [rax+28h]
0x1800199cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199d4  mov     edi, eax
0x1800199d6  test    eax, eax
0x1800199d8  js      short loc_180019997
0x1800199da  mov     rbp, [rbx]
0x1800199dd  mov     r15d, esi
0x1800199e0  mov     dword ptr [rsp+0D8h+var_A8], 0
0x1800199e8  mov     rax, [r12]
0x1800199ec  lea     r9, [rsp+0D8h+var_A8]
0x1800199f1  mov     r8d, r15d
0x1800199f4  mov     rdx, rbp
0x1800199f7  mov     rcx, r12
0x1800199fa  mov     rax, [rax+18h]
0x1800199fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a03  mov     edi, eax
0x180019a05  test    eax, eax
0x180019a07  js      short loc_180019997
0x180019a09  mov     ecx, dword ptr [rsp+0D8h+var_A8]
0x180019a0d  add     rbp, rcx
0x180019a10  sub     r15d, ecx
0x180019a13  test    ecx, ecx
0x180019a15  jnz     short loc_1800199E8
0x180019a17  mov     [r14], esi
0x180019a1a  jmp     short loc_1800199AC
0x180019a1c  mov     eax, 80070057h
0x180019a21  mov     rcx, [rsp+0D8h+var_48]
0x180019a29  xor     rcx, rsp; StackCookie
0x180019a2c  call    __security_check_cookie
0x180019a31  add     rsp, 0A0h
0x180019a38  pop     r15
0x180019a3a  pop     r14
0x180019a3c  pop     r12
0x180019a3e  pop     rdi
0x180019a3f  pop     rsi
0x180019a40  pop     rbp
0x180019a41  pop     rbx
0x180019a42  retn
```
