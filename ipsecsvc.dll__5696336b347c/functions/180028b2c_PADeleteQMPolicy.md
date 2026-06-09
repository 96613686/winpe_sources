# PADeleteQMPolicy

- ea: `0x180028b2c`
- end: `0x180028c21`
- name: `PADeleteQMPolicy`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000cd90`
- `0x18000cfa8`
- `0x18002b9a8`

## callees

- `0x18000e510`
- `0x180018a94`
- `0x18001cc18`
- `0x180027954`
- `0x18002833c`
- `0x180028b2c`

## pseudocode

```c
__int64 __fastcall PADeleteQMPolicy(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 QMPolicyState; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rbx
  unsigned int v10; // edi
  unsigned int v11; // eax
  char *v12; // rax
  LPVOID *v13; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_23b1f3110213325002571ebd730d21df_Traceguids, a1);
  QMPolicyState = FindQMPolicyState(a1, a2, a3, a4);
  v8 = QMPolicyState;
  if ( !QMPolicyState )
    return 0;
  if ( (*(_DWORD *)(QMPolicyState + 60))-- != 1 )
    return 0;
  v10 = 0;
  if ( *(_DWORD *)(QMPolicyState + 64)
    && (v11 = DeleteQMPolicy(v7, v6, *(_WORD **)(QMPolicyState + 16)), (v10 = v11) != 0) )
  {
    ++*(_DWORD *)(v8 + 60);
    *(_DWORD *)(v8 + 68) = v11;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_23b1f3110213325002571ebd730d21df_Traceguids, v11);
  }
  else
  {
    v12 = (char *)gpQMPolicyState;
    v13 = &gpQMPolicyState;
    while ( v12 && v12 != (char *)v8 )
    {
      v13 = (LPVOID *)(v12 + 72);
      v12 = (char *)*((_QWORD *)v12 + 9);
    }
    if ( *v13 )
      *v13 = *(LPVOID *)(v8 + 72);
    PAFreeMMPolicyState((LPVOID)v8);
  }
  return v10;
}

```

## disassembly

```asm
0x180028b2c  mov     [rsp+arg_8], rbx
0x180028b31  mov     [rsp+arg_10], rsi
0x180028b36  push    rdi
0x180028b37  sub     rsp, 30h
0x180028b3b  mov     rbx, rcx
0x180028b3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b45  lea     rsi, WPP_GLOBAL_Control
0x180028b4c  cmp     rcx, rsi
0x180028b4f  jz      short loc_180028B6F
0x180028b51  test    byte ptr [rcx+1Ch], 4
0x180028b55  jz      short loc_180028B6F
0x180028b57  mov     rcx, [rcx+10h]
0x180028b5b  lea     r8, WPP_23b1f3110213325002571ebd730d21df_Traceguids
0x180028b62  mov     edx, 1Ch
0x180028b67  mov     r9, rbx
0x180028b6a  call    WPP_SF__guid_
0x180028b6f  mov     rcx, rbx
0x180028b72  call    FindQMPolicyState
0x180028b77  mov     rbx, rax
0x180028b7a  test    rax, rax
0x180028b7d  jz      loc_180028C0F
0x180028b83  add     dword ptr [rax+3Ch], 0FFFFFFFFh
0x180028b87  jnz     loc_180028C0F
0x180028b8d  xor     edi, edi
0x180028b8f  cmp     [rax+40h], edi
0x180028b92  jz      short loc_180028BD5
0x180028b94  mov     r8, [rax+10h]
0x180028b98  call    DeleteQMPolicy
0x180028b9d  mov     edi, eax
0x180028b9f  test    eax, eax
0x180028ba1  jz      short loc_180028BD5
0x180028ba3  inc     dword ptr [rbx+3Ch]
0x180028ba6  mov     [rbx+44h], eax
0x180028ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x180028bb0  cmp     rcx, rsi
0x180028bb3  jz      short loc_180028C0B
0x180028bb5  test    byte ptr [rcx+1Ch], 10h
0x180028bb9  jz      short loc_180028C0B
0x180028bbb  mov     rcx, [rcx+10h]
0x180028bbf  lea     r8, WPP_23b1f3110213325002571ebd730d21df_Traceguids
0x180028bc6  mov     edx, 1Dh
0x180028bcb  mov     r9d, eax
0x180028bce  call    WPP_SF_d
0x180028bd3  jmp     short loc_180028C0B
0x180028bd5  mov     rax, cs:gpQMPolicyState
0x180028bdc  lea     rcx, gpQMPolicyState
0x180028be3  jmp     short loc_180028BF1
0x180028be5  cmp     rax, rbx
0x180028be8  jz      short loc_180028BF6
0x180028bea  lea     rcx, [rax+48h]
0x180028bee  mov     rax, [rcx]
0x180028bf1  test    rax, rax
0x180028bf4  jnz     short loc_180028BE5
0x180028bf6  cmp     qword ptr [rcx], 0
0x180028bfa  jz      short loc_180028C03
0x180028bfc  mov     rax, [rbx+48h]
0x180028c00  mov     [rcx], rax
0x180028c03  mov     rcx, rbx; lpMem
0x180028c06  call    PAFreeMMPolicyState
0x180028c0b  mov     eax, edi
0x180028c0d  jmp     short loc_180028C11
0x180028c0f  xor     eax, eax
0x180028c11  mov     rbx, [rsp+38h+arg_8]
0x180028c16  mov     rsi, [rsp+38h+arg_10]
0x180028c1b  add     rsp, 30h
0x180028c1f  pop     rdi
0x180028c20  retn
```
