# ClientData::GetCache(ulong,void const * *,long *,ulong *)

- ea: `0x18009a050`
- end: `0x18009a21a`
- name: `?GetCache@ClientData@@UEAAHKPEAPEBXPEAJPEAK@Z`
- size: `458`
- prototype: `__int64 __fastcall(ClientData *__hidden this, unsigned int, const void **, int *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800055d0`
- `0x180009d00`
- `0x18000da60`
- `0x18007ac50`
- `0x18007ba24`
- `0x18009a050`
- `0x1800a3520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a1af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a1af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a0a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a0a8`
- `TextShaping!BuildOtlCache` at `0x18009a135`
- `TextShaping!BuildOtlCache` at `0x18009a135`

## pseudocode

```c
__int64 __fastcall ClientData::GetCache(ClientData *this, unsigned int a2, const void **a3, int *a4, unsigned int *a5)
{
  __int64 v6; // rcx
  int v9; // eax
  void *v10; // rsi
  __int64 v11; // rax
  __int64 result; // rax
  unsigned int v13; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14; // [rsp+34h] [rbp-CCh] BYREF
  void *Src; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE *v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h]
  __int16 v18; // [rsp+4Ch] [rbp-B4h]
  _BYTE v19[256]; // [rsp+50h] [rbp-B0h] BYREF

  v6 = *((_QWORD *)this + 4);
  if ( (unsigned __int64)(v6 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    result = 2561;
    *a3 = 0;
    *a4 = 0;
    *a5 = a2;
  }
  else
  {
    if ( *(_DWORD *)(v6 + 48) == -1 )
    {
      EnterCriticalSection(&csCache);
      if ( *(_DWORD *)(*((_QWORD *)this + 4) + 48LL) == -1 )
      {
        Src = 0;
        v13 = 0;
        v14 = 0;
        memset_0(v19, 0, sizeof(v19));
        v17 = 16777217;
        v16 = v19;
        v18 = 0;
        v9 = UspAllocTemp(0x4000, &Src);
        v10 = Src;
        if ( v9 >= 0
          && !BuildOtlCache((ClientData *)((char *)this + 40), 0x4000, (struct otlList *)&v16, Src, (int *)&v13, &v14) )
        {
          v11 = *((_QWORD *)this + 4);
          if ( (int)v13 <= 0 )
          {
            *(_DWORD *)(v11 + 48) = 0;
            *(_DWORD *)(*((_QWORD *)this + 4) + 52LL) = v14;
            *(_QWORD *)(*((_QWORD *)this + 4) + 24LL) = 0;
          }
          else if ( (int)UspAllocCache(v13, v11 + 24) >= 0 )
          {
            *(_DWORD *)(*((_QWORD *)this + 4) + 48LL) = v13;
            *(_DWORD *)(*((_QWORD *)this + 4) + 52LL) = v14;
            memmove_0(*(void **)(*((_QWORD *)this + 4) + 24LL), v10, (int)v13);
          }
        }
        if ( v10 )
          UspFreeMem(v10);
      }
      LeaveCriticalSection(&csCache);
    }
    *a3 = *(const void **)(*((_QWORD *)this + 4) + 24LL);
    *a4 = *(_DWORD *)(*((_QWORD *)this + 4) + 48LL);
    *a5 = *(_DWORD *)(*((_QWORD *)this + 4) + 52LL);
    return *(_QWORD *)(*((_QWORD *)this + 4) + 24LL) == 0 ? 0xA01 : 0;
  }
  return result;
}

```

## disassembly

```asm
0x18009a050  push    rbp
0x18009a052  push    rbx
0x18009a053  push    rsi
0x18009a054  push    rdi
0x18009a055  push    r12
0x18009a057  push    r14
0x18009a059  push    r15
0x18009a05b  lea     rbp, [rsp-60h]
0x18009a060  sub     rsp, 160h
0x18009a067  mov     rax, cs:__security_cookie
0x18009a06e  xor     rax, rsp
0x18009a071  mov     [rbp+90h+var_40], rax
0x18009a075  mov     r12, [rbp+90h+arg_20]
0x18009a07c  mov     rdi, rcx
0x18009a07f  mov     rcx, [rcx+20h]
0x18009a083  mov     r15, r9
0x18009a086  mov     r14, r8
0x18009a089  lea     rax, [rcx-1]
0x18009a08d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009a091  ja      loc_18009A1EB
0x18009a097  cmp     dword ptr [rcx+30h], 0FFFFFFFFh
0x18009a09b  jnz     loc_18009A1B5
0x18009a0a1  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009a0a8  call    cs:__imp_EnterCriticalSection
0x18009a0ae  mov     rax, [rdi+20h]
0x18009a0b2  cmp     dword ptr [rax+30h], 0FFFFFFFFh
0x18009a0b6  jnz     loc_18009A1A8
0x18009a0bc  xor     ebx, ebx
0x18009a0be  lea     rcx, [rsp+190h+var_140]; void *
0x18009a0c3  xor     edx, edx; Val
0x18009a0c5  mov     [rsp+190h+Src], rbx
0x18009a0ca  mov     r8d, 100h; Size
0x18009a0d0  mov     [rsp+190h+var_160], ebx
0x18009a0d4  mov     [rsp+190h+var_15C], ebx
0x18009a0d8  call    memset_0
0x18009a0dd  lea     rax, [rsp+190h+var_140]
0x18009a0e2  mov     [rsp+190h+var_148], 1000001h
0x18009a0ea  lea     rdx, [rsp+190h+Src]
0x18009a0ef  mov     [rsp+190h+var_150], rax
0x18009a0f4  mov     ecx, 4000h
0x18009a0f9  mov     [rsp+190h+var_144], bx
0x18009a0fe  call    UspAllocTemp
0x18009a103  mov     rsi, [rsp+190h+Src]
0x18009a108  test    eax, eax
0x18009a10a  js      loc_18009A19B
0x18009a110  lea     rax, [rsp+190h+var_15C]
0x18009a115  mov     r9, rsi
0x18009a118  mov     [rsp+190h+var_168], rax
0x18009a11d  lea     rcx, [rdi+28h]
0x18009a121  lea     rax, [rsp+190h+var_160]
0x18009a126  mov     edx, 4000h
0x18009a12b  lea     r8, [rsp+190h+var_150]
0x18009a130  mov     [rsp+190h+var_170], rax
0x18009a135  call    cs:__imp_?BuildOtlCache@@YAHPEBUotlRunProp@@JPEAVotlList@@PEAXPEAJPEAK@Z; BuildOtlCache(otlRunProp const *,long,otlList *,void *,long *,ulong *)
0x18009a13b  test    eax, eax
0x18009a13d  jnz     short loc_18009A19B
0x18009a13f  mov     ecx, [rsp+190h+var_160]
0x18009a143  mov     rax, [rdi+20h]
0x18009a147  test    ecx, ecx
0x18009a149  jle     short loc_18009A185
0x18009a14b  lea     rdx, [rax+18h]
0x18009a14f  call    UspAllocCache
0x18009a154  test    eax, eax
0x18009a156  js      short loc_18009A19B
0x18009a158  mov     rcx, [rdi+20h]
0x18009a15c  mov     rdx, rsi; Src
0x18009a15f  mov     eax, [rsp+190h+var_160]
0x18009a163  mov     [rcx+30h], eax
0x18009a166  mov     rcx, [rdi+20h]
0x18009a16a  mov     eax, [rsp+190h+var_15C]
0x18009a16e  mov     [rcx+34h], eax
0x18009a171  mov     rcx, [rdi+20h]
0x18009a175  movsxd  r8, [rsp+190h+var_160]; Size
0x18009a17a  mov     rcx, [rcx+18h]; void *
0x18009a17e  call    memmove_0
0x18009a183  jmp     short loc_18009A19B
0x18009a185  mov     [rax+30h], ebx
0x18009a188  mov     eax, [rsp+190h+var_15C]
0x18009a18c  mov     rdx, [rdi+20h]
0x18009a190  mov     [rdx+34h], eax
0x18009a193  mov     rax, [rdi+20h]
0x18009a197  mov     [rax+18h], rbx
0x18009a19b  test    rsi, rsi
0x18009a19e  jz      short loc_18009A1A8
0x18009a1a0  mov     rcx, rsi; lpMem
0x18009a1a3  call    UspFreeMem
0x18009a1a8  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009a1af  call    cs:__imp_LeaveCriticalSection
0x18009a1b5  mov     rax, [rdi+20h]
0x18009a1b9  mov     rcx, [rax+18h]
0x18009a1bd  mov     [r14], rcx
0x18009a1c0  mov     rax, [rdi+20h]
0x18009a1c4  mov     ecx, [rax+30h]
0x18009a1c7  mov     [r15], ecx
0x18009a1ca  mov     rax, [rdi+20h]
0x18009a1ce  mov     ecx, [rax+34h]
0x18009a1d1  mov     [r12], ecx
0x18009a1d5  mov     rax, [rdi+20h]
0x18009a1d9  mov     rcx, [rax+18h]
0x18009a1dd  neg     rcx
0x18009a1e0  sbb     eax, eax
0x18009a1e2  not     eax
0x18009a1e4  and     eax, 0A01h
0x18009a1e9  jmp     short loc_18009A1FC
0x18009a1eb  xor     ebx, ebx
0x18009a1ed  mov     eax, 0A01h
0x18009a1f2  mov     [r8], rbx
0x18009a1f5  mov     [r9], ebx
0x18009a1f8  mov     [r12], edx
0x18009a1fc  mov     rcx, [rbp+90h+var_40]
0x18009a200  xor     rcx, rsp; StackCookie
0x18009a203  call    __security_check_cookie
0x18009a208  add     rsp, 160h
0x18009a20f  pop     r15
0x18009a211  pop     r14
0x18009a213  pop     r12
0x18009a215  pop     rdi
0x18009a216  pop     rsi
0x18009a217  pop     rbx
0x18009a218  pop     rbp
0x18009a219  retn
```
