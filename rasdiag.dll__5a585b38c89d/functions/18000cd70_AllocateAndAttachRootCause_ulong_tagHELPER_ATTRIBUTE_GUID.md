# AllocateAndAttachRootCause(ulong *,tagHELPER_ATTRIBUTE * *,_GUID)

- ea: `0x18000cd70`
- end: `0x18000cf5b`
- name: `?AllocateAndAttachRootCause@@YAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@U_GUID@@@Z`
- size: `491`
- prototype: `__int64 __fastcall(unsigned int *, LPVOID *, struct _GUID *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800069f0`
- `0x1800085e0`

## callees

- `0x18000cd70`
- `0x18000dec6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cdd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cdd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf2f`

## pseudocode

```c
__int64 __fastcall AllocateAndAttachRootCause(unsigned int *a1, LPVOID *a2, struct _GUID *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rbx
  struct tagHELPER_ATTRIBUTE *v8; // rax
  _QWORD *v10; // r12
  const wchar_t *v11; // r15
  __int64 v12; // rcx
  const wchar_t *v13; // rax
  __int64 v14; // rbp
  _WORD *v15; // rax
  _WORD *v16; // r8
  unsigned __int64 v17; // rdx
  __int64 v18; // rax
  _WORD *v19; // rcx
  _OWORD Buf2[4]; // [rsp+20h] [rbp-48h] BYREF

  if ( a1 && a2 && !*a2 && !*a1 )
  {
    Buf2[0] = 0;
    if ( !memcmp_0(a3, Buf2, 0x10u) )
    {
      v6 = 0;
LABEL_34:
      *a2 = 0;
      *a1 = 0;
      return v6;
    }
    v7 = 144;
    v8 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(0x90u);
    *a2 = v8;
    if ( !v8 )
      return 2147942414LL;
    do
    {
      LOBYTE(v8->pwszName) = 0;
      v8 = (struct tagHELPER_ATTRIBUTE *)((char *)v8 + 1);
      --v7;
    }
    while ( v7 );
    *((_DWORD *)*a2 + 2) = 11;
    v10 = *a2;
    if ( *a2 )
    {
      v11 = L"rootcauseid";
      v12 = 259;
      v13 = L"rootcauseid";
      do
      {
        if ( !*v13 )
          break;
        ++v13;
        --v12;
      }
      while ( v12 );
      v6 = v12 == 0 ? 0x80070057 : 0;
      v14 = (259 - v12) & -(__int64)(v12 != 0);
      if ( v12 )
      {
        v15 = CoTaskMemAlloc(2 * v14 + 2);
        *v10 = v15;
        v16 = v15;
        if ( v15 )
        {
          v17 = v14 + 1;
          if ( v14 == -1 )
          {
            v6 = -2147024809;
          }
          else if ( v17 <= 0x7FFFFFFF )
          {
            v18 = 2147483646;
            do
            {
              if ( !v18 )
                break;
              if ( !*v11 )
                break;
              *v16++ = *v11++;
              --v18;
              --v17;
            }
            while ( v17 );
            v19 = v16 - 1;
            if ( v17 )
              v19 = v16;
            v6 = v17 == 0 ? 0x8007007A : 0;
            *v19 = 0;
          }
          else
          {
            v6 = -2147024809;
            *v15 = 0;
          }
          if ( (v6 & 0x80000000) == 0 )
          {
            *((struct _GUID *)*a2 + 1) = *a3;
            *a1 = 1;
            return v6;
          }
        }
        else
        {
          v6 = -2147024882;
        }
      }
    }
    else
    {
      v6 = -2147024809;
    }
    if ( *a2 )
    {
      CoTaskMemFree(*(LPVOID *)*a2);
      CoTaskMemFree(*a2);
      goto LABEL_34;
    }
    return v6;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000cd70  push    rbx
0x18000cd72  push    rbp
0x18000cd73  push    rdi
0x18000cd74  push    r12
0x18000cd76  push    r13
0x18000cd78  push    r14
0x18000cd7a  push    r15
0x18000cd7c  sub     rsp, 30h
0x18000cd80  xor     ebp, ebp
0x18000cd82  mov     r13, r8
0x18000cd85  mov     rdi, rdx
0x18000cd88  mov     r14, rcx
0x18000cd8b  test    rcx, rcx
0x18000cd8e  jz      loc_18000CF45
0x18000cd94  test    rdx, rdx
0x18000cd97  jz      loc_18000CF45
0x18000cd9d  cmp     [rdx], rbp
0x18000cda0  jnz     loc_18000CF45
0x18000cda6  cmp     [rcx], ebp
0x18000cda8  jnz     loc_18000CF45
0x18000cdae  xorps   xmm0, xmm0
0x18000cdb1  lea     r8d, [rbp+10h]; Size
0x18000cdb5  lea     rdx, [rsp+68h+Buf2]; Buf2
0x18000cdba  mov     rcx, r13; Buf1
0x18000cdbd  movups  [rsp+68h+Buf2], xmm0
0x18000cdc2  call    memcmp_0
0x18000cdc7  test    eax, eax
0x18000cdc9  jnz     short loc_18000CDD2
0x18000cdcb  mov     ebx, ebp
0x18000cdcd  jmp     loc_18000CF3B
0x18000cdd2  mov     ebx, 90h
0x18000cdd7  mov     ecx, ebx; cb
0x18000cdd9  call    cs:__imp_CoTaskMemAlloc
0x18000cde0  nop     dword ptr [rax+rax+00h]
0x18000cde5  mov     [rdi], rax
0x18000cde8  test    rax, rax
0x18000cdeb  jnz     short loc_18000CDF7
0x18000cded  mov     eax, 8007000Eh
0x18000cdf2  jmp     loc_18000CF4A
0x18000cdf7  mov     [rax], bpl
0x18000cdfa  inc     rax
0x18000cdfd  sub     rbx, 1
0x18000ce01  jnz     short loc_18000CDF7
0x18000ce03  mov     rax, [rdi]
0x18000ce06  mov     dword ptr [rax+8], 0Bh
0x18000ce0d  mov     r12, [rdi]
0x18000ce10  test    r12, r12
0x18000ce13  jz      loc_18000CF10
0x18000ce19  mov     edx, 103h
0x18000ce1e  lea     r15, aRootcauseid; "rootcauseid"
0x18000ce25  mov     ecx, edx
0x18000ce27  mov     rax, r15
0x18000ce2a  cmp     [rax], bp
0x18000ce2d  jz      short loc_18000CE39
0x18000ce2f  add     rax, 2
0x18000ce33  sub     rcx, 1
0x18000ce37  jnz     short loc_18000CE2A
0x18000ce39  mov     rax, rcx
0x18000ce3c  neg     rax
0x18000ce3f  mov     rax, rcx
0x18000ce42  sbb     ebx, ebx
0x18000ce44  sub     rdx, rcx
0x18000ce47  not     ebx
0x18000ce49  and     ebx, 80070057h
0x18000ce4f  neg     rax
0x18000ce52  sbb     rbp, rbp
0x18000ce55  and     rbp, rdx
0x18000ce58  test    rcx, rcx
0x18000ce5b  jz      short loc_18000CE82
0x18000ce5d  lea     rcx, ds:2[rbp*2]; cb
0x18000ce65  call    cs:__imp_CoTaskMemAlloc
0x18000ce6c  nop     dword ptr [rax+rax+00h]
0x18000ce71  mov     [r12], rax
0x18000ce75  mov     r8, rax
0x18000ce78  test    rax, rax
0x18000ce7b  jnz     short loc_18000CE89
0x18000ce7d  mov     ebx, 8007000Eh
0x18000ce82  xor     ebp, ebp
0x18000ce84  jmp     loc_18000CF15
0x18000ce89  lea     rdx, [rbp+1]
0x18000ce8d  xor     ebp, ebp
0x18000ce8f  test    rdx, rdx
0x18000ce92  jz      short loc_18000CEE9
0x18000ce94  cmp     rdx, 7FFFFFFFh
0x18000ce9b  jbe     short loc_18000CEA4
0x18000ce9d  mov     ebx, 80070057h
0x18000cea2  jmp     short loc_18000CEF3
0x18000cea4  mov     eax, 7FFFFFFEh
0x18000cea9  test    rax, rax
0x18000ceac  jz      short loc_18000CECC
0x18000ceae  movzx   ecx, word ptr [r15]
0x18000ceb2  test    cx, cx
0x18000ceb5  jz      short loc_18000CECC
0x18000ceb7  mov     [r8], cx
0x18000cebb  add     r15, 2
0x18000cebf  add     r8, 2
0x18000cec3  dec     rax
0x18000cec6  sub     rdx, 1
0x18000ceca  jnz     short loc_18000CEA9
0x18000cecc  test    rdx, rdx
0x18000cecf  lea     rcx, [r8-2]
0x18000ced3  cmovnz  rcx, r8
0x18000ced7  neg     rdx
0x18000ceda  sbb     ebx, ebx
0x18000cedc  not     ebx
0x18000cede  and     ebx, 8007007Ah
0x18000cee4  mov     [rcx], bp
0x18000cee7  jmp     short loc_18000CEF6
0x18000cee9  mov     ebx, 80070057h
0x18000ceee  test    rdx, rdx
0x18000cef1  jz      short loc_18000CEF6
0x18000cef3  mov     [rax], bp
0x18000cef6  test    ebx, ebx
0x18000cef8  js      short loc_18000CF15
0x18000cefa  mov     rax, [rdi]
0x18000cefd  movaps  xmm0, xmmword ptr [r13+0]
0x18000cf02  movdqu  xmmword ptr [rax+10h], xmm0
0x18000cf07  mov     dword ptr [r14], 1
0x18000cf0e  jmp     short loc_18000CF41
0x18000cf10  mov     ebx, 80070057h
0x18000cf15  mov     rcx, [rdi]
0x18000cf18  test    rcx, rcx
0x18000cf1b  jz      short loc_18000CF41
0x18000cf1d  mov     rcx, [rcx]; pv
0x18000cf20  call    cs:__imp_CoTaskMemFree
0x18000cf27  nop     dword ptr [rax+rax+00h]
0x18000cf2c  mov     rcx, [rdi]; pv
0x18000cf2f  call    cs:__imp_CoTaskMemFree
0x18000cf36  nop     dword ptr [rax+rax+00h]
0x18000cf3b  mov     [rdi], rbp
0x18000cf3e  mov     [r14], ebp
0x18000cf41  mov     eax, ebx
0x18000cf43  jmp     short loc_18000CF4A
0x18000cf45  mov     eax, 80070057h
0x18000cf4a  add     rsp, 30h
0x18000cf4e  pop     r15
0x18000cf50  pop     r14
0x18000cf52  pop     r13
0x18000cf54  pop     r12
0x18000cf56  pop     rdi
0x18000cf57  pop     rbp
0x18000cf58  pop     rbx
0x18000cf59  retn
```
