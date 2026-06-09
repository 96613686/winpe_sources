# ClientData::GetCache(ulong,void const * *,long *,ulong *)

- ea: `0x18009cdc0`
- end: `0x18009cf9d`
- name: `?GetCache@ClientData@@UEAAHKPEAPEBXPEAJPEAK@Z`
- size: `477`
- prototype: `__int64 __fastcall(ClientData *__hidden this, unsigned int, const void **, int *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180006e00`
- `0x18000d040`
- `0x18001ac40`
- `0x18007f800`
- `0x180080604`
- `0x18009cdc0`
- `0x1800a68e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009cf2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009cf2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ce18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ce18`
- `TextShaping!BuildOtlCache` at `0x18009ceab`
- `TextShaping!BuildOtlCache` at `0x18009ceab`

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
0x18009cdc0  push    rbp
0x18009cdc2  push    rbx
0x18009cdc3  push    rsi
0x18009cdc4  push    rdi
0x18009cdc5  push    r12
0x18009cdc7  push    r14
0x18009cdc9  push    r15
0x18009cdcb  lea     rbp, [rsp-60h]
0x18009cdd0  sub     rsp, 160h
0x18009cdd7  mov     rax, cs:__security_cookie
0x18009cdde  xor     rax, rsp
0x18009cde1  mov     [rbp+90h+var_40], rax
0x18009cde5  mov     r12, [rbp+90h+arg_20]
0x18009cdec  mov     rdi, rcx
0x18009cdef  mov     rcx, [rcx+20h]
0x18009cdf3  mov     r15, r9
0x18009cdf6  mov     r14, r8
0x18009cdf9  lea     rax, [rcx-1]
0x18009cdfd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009ce01  ja      loc_18009CF6D
0x18009ce07  cmp     dword ptr [rcx+30h], 0FFFFFFFFh
0x18009ce0b  jnz     loc_18009CF37
0x18009ce11  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009ce18  call    cs:__imp_EnterCriticalSection
0x18009ce1f  nop     dword ptr [rax+rax+00h]
0x18009ce24  mov     rax, [rdi+20h]
0x18009ce28  cmp     dword ptr [rax+30h], 0FFFFFFFFh
0x18009ce2c  jnz     loc_18009CF24
0x18009ce32  xor     ebx, ebx
0x18009ce34  lea     rcx, [rsp+190h+var_140]; void *
0x18009ce39  xor     edx, edx; Val
0x18009ce3b  mov     [rsp+190h+Src], rbx
0x18009ce40  mov     r8d, 100h; Size
0x18009ce46  mov     [rsp+190h+var_160], ebx
0x18009ce4a  mov     [rsp+190h+var_15C], ebx
0x18009ce4e  call    memset_0
0x18009ce53  lea     rax, [rsp+190h+var_140]
0x18009ce58  mov     [rsp+190h+var_148], 1000001h
0x18009ce60  lea     rdx, [rsp+190h+Src]
0x18009ce65  mov     [rsp+190h+var_150], rax
0x18009ce6a  mov     ecx, 4000h
0x18009ce6f  mov     [rsp+190h+var_144], bx
0x18009ce74  call    UspAllocTemp
0x18009ce79  mov     rsi, [rsp+190h+Src]
0x18009ce7e  test    eax, eax
0x18009ce80  js      loc_18009CF17
0x18009ce86  lea     rax, [rsp+190h+var_15C]
0x18009ce8b  mov     r9, rsi
0x18009ce8e  mov     [rsp+190h+var_168], rax
0x18009ce93  lea     rcx, [rdi+28h]
0x18009ce97  lea     rax, [rsp+190h+var_160]
0x18009ce9c  mov     edx, 4000h
0x18009cea1  lea     r8, [rsp+190h+var_150]
0x18009cea6  mov     [rsp+190h+var_170], rax
0x18009ceab  call    cs:__imp_?BuildOtlCache@@YAHPEBUotlRunProp@@JPEAVotlList@@PEAXPEAJPEAK@Z; BuildOtlCache(otlRunProp const *,long,otlList *,void *,long *,ulong *)
0x18009ceb2  nop     dword ptr [rax+rax+00h]
0x18009ceb7  test    eax, eax
0x18009ceb9  jnz     short loc_18009CF17
0x18009cebb  mov     ecx, [rsp+190h+var_160]
0x18009cebf  mov     rax, [rdi+20h]
0x18009cec3  test    ecx, ecx
0x18009cec5  jle     short loc_18009CF01
0x18009cec7  lea     rdx, [rax+18h]
0x18009cecb  call    UspAllocCache
0x18009ced0  test    eax, eax
0x18009ced2  js      short loc_18009CF17
0x18009ced4  mov     rcx, [rdi+20h]
0x18009ced8  mov     rdx, rsi; Src
0x18009cedb  mov     eax, [rsp+190h+var_160]
0x18009cedf  mov     [rcx+30h], eax
0x18009cee2  mov     rcx, [rdi+20h]
0x18009cee6  mov     eax, [rsp+190h+var_15C]
0x18009ceea  mov     [rcx+34h], eax
0x18009ceed  mov     rcx, [rdi+20h]
0x18009cef1  movsxd  r8, [rsp+190h+var_160]; Size
0x18009cef6  mov     rcx, [rcx+18h]; void *
0x18009cefa  call    memmove_0
0x18009ceff  jmp     short loc_18009CF17
0x18009cf01  mov     [rax+30h], ebx
0x18009cf04  mov     eax, [rsp+190h+var_15C]
0x18009cf08  mov     rdx, [rdi+20h]
0x18009cf0c  mov     [rdx+34h], eax
0x18009cf0f  mov     rax, [rdi+20h]
0x18009cf13  mov     [rax+18h], rbx
0x18009cf17  test    rsi, rsi
0x18009cf1a  jz      short loc_18009CF24
0x18009cf1c  mov     rcx, rsi; lpMem
0x18009cf1f  call    UspFreeMem
0x18009cf24  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009cf2b  call    cs:__imp_LeaveCriticalSection
0x18009cf32  nop     dword ptr [rax+rax+00h]
0x18009cf37  mov     rax, [rdi+20h]
0x18009cf3b  mov     rcx, [rax+18h]
0x18009cf3f  mov     [r14], rcx
0x18009cf42  mov     rax, [rdi+20h]
0x18009cf46  mov     ecx, [rax+30h]
0x18009cf49  mov     [r15], ecx
0x18009cf4c  mov     rax, [rdi+20h]
0x18009cf50  mov     ecx, [rax+34h]
0x18009cf53  mov     [r12], ecx
0x18009cf57  mov     rax, [rdi+20h]
0x18009cf5b  mov     rcx, [rax+18h]
0x18009cf5f  neg     rcx
0x18009cf62  sbb     eax, eax
0x18009cf64  not     eax
0x18009cf66  and     eax, 0A01h
0x18009cf6b  jmp     short loc_18009CF7E
0x18009cf6d  xor     ebx, ebx
0x18009cf6f  mov     eax, 0A01h
0x18009cf74  mov     [r8], rbx
0x18009cf77  mov     [r9], ebx
0x18009cf7a  mov     [r12], edx
0x18009cf7e  mov     rcx, [rbp+90h+var_40]
0x18009cf82  xor     rcx, rsp; StackCookie
0x18009cf85  call    __security_check_cookie
0x18009cf8a  add     rsp, 160h
0x18009cf91  pop     r15
0x18009cf93  pop     r14
0x18009cf95  pop     r12
0x18009cf97  pop     rdi
0x18009cf98  pop     rsi
0x18009cf99  pop     rbx
0x18009cf9a  pop     rbp
0x18009cf9b  retn
```
