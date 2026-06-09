# CMCreateTransformExtInternal

- ea: `0x18001d7a0`
- end: `0x18001d923`
- name: `CMCreateTransformExtInternal`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001d930`

## callees

- `0x180002344`
- `0x1800067e4`
- `0x1800069f0`
- `0x18001d7a0`
- `0x18003d040`

## import_xrefs

- `mscms!CloseColorProfile` at `0x18001d8cf`
- `mscms!CloseColorProfile` at `0x18001d8cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d8db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d8db`

## pseudocode

```c
__int64 __fastcall CMCreateTransformExtInternal(__int64 *a1, int a2, int a3, void *a4, __int64 a5, __int64 a6)
{
  int v9; // esi
  int v10; // r8d
  int v11; // r8d
  int v12; // eax
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rdx
  void *v16; // rax
  int v17; // ecx
  void *v19; // [rsp+40h] [rbp-40h] BYREF
  __int64 v20; // [rsp+48h] [rbp-38h]
  __int64 v21; // [rsp+50h] [rbp-30h]
  __int64 v22; // [rsp+58h] [rbp-28h] BYREF
  __int64 v23; // [rsp+60h] [rbp-20h] BYREF
  int v24; // [rsp+68h] [rbp-18h] BYREF
  int v25; // [rsp+6Ch] [rbp-14h]
  int v26; // [rsp+70h] [rbp-10h]

  *a1 = 0;
  v22 = 0;
  v23 = 0;
  v21 = 0;
  v24 = 1;
  v9 = 2;
  v10 = a3 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 == 6 )
        v25 = 3;
      else
        v25 = 0;
    }
    else
    {
      v25 = 1;
    }
  }
  else
  {
    v25 = 2;
  }
  v19 = a4;
  if ( a5 )
  {
    v20 = a5;
    v9 = 3;
    v21 = a6;
    v26 = 1;
  }
  else
  {
    v20 = a6;
  }
  v12 = CMCreateMultiProfileTransformInternal(&v22, (__int64)&v19, v9, &v24, v9, a2);
  v13 = v22;
  LODWORD(v14) = v12;
  if ( !v12 && a2 < 0 )
  {
    v15 = (unsigned int)(v9 - 1);
    v16 = *(&v19 + v15);
    v17 = *(&v24 + v15);
    *(&v19 + v15) = a4;
    v19 = v16;
    *(&v24 + v15) = v24;
    v24 = v17;
    LODWORD(v14) = CMCreateMultiProfileTransformInternal(&v23, (__int64)&v19, v9, &v24, v9, a2);
    if ( (_DWORD)v14 )
      LHColorWorldClose(v13);
    else
      *(_QWORD *)(v13 + 376) = v23;
  }
  CloseColorProfile(a4);
  if ( (_DWORD)v14 )
  {
    SetLastError(v14);
    v14 = (unsigned __int8)v14;
  }
  else
  {
    v14 = StoreTransform(v13);
    if ( v14 == 8 )
      LHColorWorldClose(v13);
  }
  *a1 = v14;
  return 0;
}

```

## disassembly

```asm
0x18001d7a0  push    rbp
0x18001d7a2  push    rbx
0x18001d7a3  push    rsi
0x18001d7a4  push    rdi
0x18001d7a5  push    r12
0x18001d7a7  push    r14
0x18001d7a9  push    r15
0x18001d7ab  mov     rbp, rsp
0x18001d7ae  sub     rsp, 80h
0x18001d7b5  mov     rax, cs:__security_cookie
0x18001d7bc  xor     rax, rsp
0x18001d7bf  mov     [rbp+var_8], rax
0x18001d7c3  mov     r12, rcx
0x18001d7c6  mov     qword ptr [rcx], 0
0x18001d7cd  mov     ecx, 1
0x18001d7d2  mov     [rbp+var_28], 0
0x18001d7da  mov     [rbp+var_20], 0
0x18001d7e2  mov     r15d, edx
0x18001d7e5  mov     [rbp+var_30], 0
0x18001d7ed  mov     r14, r9
0x18001d7f0  mov     [rbp+var_18], ecx
0x18001d7f3  lea     edx, [rcx+2]
0x18001d7f6  lea     esi, [rcx+1]
0x18001d7f9  sub     r8d, ecx
0x18001d7fc  jz      short loc_18001D81C
0x18001d7fe  sub     r8d, ecx
0x18001d801  jz      short loc_18001D817
0x18001d803  cmp     r8d, 6
0x18001d807  jz      short loc_18001D812
0x18001d809  mov     [rbp+var_14], 0
0x18001d810  jmp     short loc_18001D81F
0x18001d812  mov     [rbp+var_14], edx
0x18001d815  jmp     short loc_18001D81F
0x18001d817  mov     [rbp+var_14], ecx
0x18001d81a  jmp     short loc_18001D81F
0x18001d81c  mov     [rbp+var_14], esi
0x18001d81f  mov     rax, [rbp+arg_20]
0x18001d823  mov     [rbp+var_40], r14
0x18001d827  test    rax, rax
0x18001d82a  jnz     short loc_18001D836
0x18001d82c  mov     rax, [rbp+arg_28]
0x18001d830  mov     [rbp+var_38], rax
0x18001d834  jmp     short loc_18001D847
0x18001d836  mov     [rbp+var_38], rax
0x18001d83a  mov     esi, edx
0x18001d83c  mov     rax, [rbp+arg_28]
0x18001d840  mov     [rbp+var_30], rax
0x18001d844  mov     [rbp+var_10], ecx
0x18001d847  mov     [rsp+80h+var_58], r15d
0x18001d84c  lea     r9, [rbp+var_18]
0x18001d850  mov     r8d, esi
0x18001d853  mov     [rsp+80h+var_60], esi
0x18001d857  lea     rdx, [rbp+var_40]
0x18001d85b  lea     rcx, [rbp+var_28]
0x18001d85f  call    CMCreateMultiProfileTransformInternal
0x18001d864  mov     rdi, [rbp+var_28]
0x18001d868  mov     ebx, eax
0x18001d86a  test    eax, eax
0x18001d86c  jnz     short loc_18001D8CC
0x18001d86e  test    r15d, r15d
0x18001d871  jns     short loc_18001D8CC
0x18001d873  lea     eax, [rsi-1]
0x18001d876  mov     [rsp+80h+var_58], r15d
0x18001d87b  mov     edx, eax
0x18001d87d  lea     r9, [rbp+var_18]
0x18001d881  mov     rax, [rbp+rax*8+var_40]
0x18001d886  mov     r8d, esi
0x18001d889  mov     [rsp+80h+var_60], esi
0x18001d88d  mov     ecx, [rbp+rdx*4+var_18]
0x18001d891  mov     [rbp+rdx*8+var_40], r14
0x18001d896  mov     [rbp+var_40], rax
0x18001d89a  mov     eax, [rbp+var_18]
0x18001d89d  mov     [rbp+rdx*4+var_18], eax
0x18001d8a1  lea     rdx, [rbp+var_40]
0x18001d8a5  mov     [rbp+var_18], ecx
0x18001d8a8  lea     rcx, [rbp+var_20]
0x18001d8ac  call    CMCreateMultiProfileTransformInternal
0x18001d8b1  mov     ebx, eax
0x18001d8b3  test    eax, eax
0x18001d8b5  jz      short loc_18001D8C1
0x18001d8b7  mov     rcx, rdi
0x18001d8ba  call    LHColorWorldClose
0x18001d8bf  jmp     short loc_18001D8CC
0x18001d8c1  mov     rax, [rbp+var_20]
0x18001d8c5  mov     [rdi+178h], rax
0x18001d8cc  mov     rcx, r14; hProfile
0x18001d8cf  call    cs:__imp_CloseColorProfile
0x18001d8d5  test    ebx, ebx
0x18001d8d7  jz      short loc_18001D8E6
0x18001d8d9  mov     ecx, ebx; dwErrCode
0x18001d8db  call    cs:__imp_SetLastError
0x18001d8e1  movzx   ebx, bl
0x18001d8e4  jmp     short loc_18001D8FF
0x18001d8e6  mov     rcx, rdi
0x18001d8e9  call    StoreTransform
0x18001d8ee  mov     rbx, rax
0x18001d8f1  cmp     rax, 8
0x18001d8f5  jnz     short loc_18001D8FF
0x18001d8f7  mov     rcx, rdi
0x18001d8fa  call    LHColorWorldClose
0x18001d8ff  mov     [r12], rbx
0x18001d903  xor     eax, eax
0x18001d905  mov     rcx, [rbp+var_8]
0x18001d909  xor     rcx, rsp; StackCookie
0x18001d90c  call    __security_check_cookie
0x18001d911  add     rsp, 80h
0x18001d918  pop     r15
0x18001d91a  pop     r14
0x18001d91c  pop     r12
0x18001d91e  pop     rdi
0x18001d91f  pop     rsi
0x18001d920  pop     rbx
0x18001d921  pop     rbp
0x18001d922  retn
```
