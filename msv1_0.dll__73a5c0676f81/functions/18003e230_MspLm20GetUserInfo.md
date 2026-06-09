# MspLm20GetUserInfo

- ea: `0x18003e230`
- end: `0x18003e377`
- name: `MspLm20GetUserInfo`
- size: `327`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, _QWORD *, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180011090`
- `0x180012d10`

## callees

- `0x18000c5d0`
- `0x18000dab4`
- `0x18000db30`
- `0x18000dc18`
- `0x1800189c0`
- `0x18003e230`
- `0x18006bd74`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18003e297`
- `ntdll!RtlLengthSid` at `0x18003e297`
- `ntdll!RtlReleaseResource` at `0x18003e34d`
- `ntdll!RtlReleaseResource` at `0x18003e34d`
- `ntdll!RtlAcquireResourceShared` at `0x18003e272`
- `ntdll!RtlAcquireResourceShared` at `0x18003e272`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MspLm20GetUserInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        unsigned int *a6,
        int *a7)
{
  int ClientBuffer; // ebx
  __int64 ActiveLogon; // rax
  __int64 v10; // rdi
  ULONG v11; // esi
  unsigned int v12; // r8d
  __int64 v13; // rbx
  __int64 v15; // [rsp+20h] [rbp-20h] BYREF
  __int128 v16; // [rsp+28h] [rbp-18h]
  __int64 v17; // [rsp+38h] [rbp-8h]

  v15 = a1;
  v17 = 0;
  v16 = 0;
  if ( a4 < 0xC )
  {
    ClientBuffer = -1073741811;
LABEL_8:
    NlpFreeClientBuffer(&v15);
    goto LABEL_9;
  }
  RtlAcquireResourceShared(&NlpActiveLogonLock, 1u);
  ActiveLogon = NlpFindActiveLogon((void *)(a2 + 4));
  v10 = ActiveLogon;
  if ( ActiveLogon )
  {
    v11 = RtlLengthSid(*(PSID *)(ActiveLogon + 64));
    v12 = *(unsigned __int16 *)(v10 + 104)
        + 78
        + *(unsigned __int16 *)(v10 + 88)
        + v11
        + *(unsigned __int16 *)(v10 + 72);
    *a6 = v12;
    ClientBuffer = NlpAllocateClientBuffer((__int64)&v15, 72, v12);
    if ( ClientBuffer >= 0 )
    {
      v13 = *((_QWORD *)&v16 + 1);
      **((_DWORD **)&v16 + 1) = 3;
      *(_DWORD *)(v13 + 64) = *(_DWORD *)(v10 + 56);
      *(_QWORD *)(v13 + 8) = v16 + (unsigned int)v17;
      memcpy_0((void *)(*((_QWORD *)&v16 + 1) + (unsigned int)v17), *(const void **)(v10 + 64), v11);
      LODWORD(v17) = v11 + v17;
      NlpPutClientString(&v15, v13 + 16, v10 + 72);
      NlpPutClientString(&v15, v13 + 32, v10 + 88);
      NlpPutClientString(&v15, v13 + 48, v10 + 104);
      ClientBuffer = NlpFlushClientBuffer((__int64)&v15, a5);
    }
  }
  else
  {
    ClientBuffer = -1073741729;
  }
  RtlReleaseResource(&NlpActiveLogonLock);
  if ( ClientBuffer < 0 )
    goto LABEL_8;
LABEL_9:
  *a7 = ClientBuffer;
  return 0;
}

```

## disassembly

```asm
0x18003e230  push    rbp
0x18003e232  push    rbx
0x18003e233  push    rsi
0x18003e234  push    rdi
0x18003e235  push    r12
0x18003e237  push    r14
0x18003e239  push    r15
0x18003e23b  mov     rbp, rsp
0x18003e23e  sub     rsp, 40h
0x18003e242  mov     [rbp+var_20], rcx
0x18003e246  xorps   xmm0, xmm0
0x18003e249  mov     [rbp+var_8], 0
0x18003e251  mov     rbx, rdx
0x18003e254  movdqu  [rbp+var_18], xmm0
0x18003e259  cmp     r9d, 0Ch
0x18003e25d  jnb     short loc_18003E269
0x18003e25f  mov     ebx, 0C000000Dh
0x18003e264  jmp     loc_18003E357
0x18003e269  mov     dl, 1; Wait
0x18003e26b  lea     rcx, NlpActiveLogonLock; Resource
0x18003e272  call    cs:__imp_RtlAcquireResourceShared
0x18003e278  lea     rcx, [rbx+4]; void *
0x18003e27c  call    NlpFindActiveLogon
0x18003e281  mov     rdi, rax
0x18003e284  test    rax, rax
0x18003e287  jnz     short loc_18003E293
0x18003e289  mov     ebx, 0C000005Fh
0x18003e28e  jmp     loc_18003E346
0x18003e293  mov     rcx, [rax+40h]; Sid
0x18003e297  call    cs:__imp_RtlLengthSid
0x18003e29d  movzx   ecx, word ptr [rdi+58h]
0x18003e2a1  mov     edx, 48h ; 'H'
0x18003e2a6  movzx   r8d, word ptr [rdi+48h]
0x18003e2ab  add     r8d, eax
0x18003e2ae  mov     esi, eax
0x18003e2b0  movzx   eax, word ptr [rdi+68h]
0x18003e2b4  add     r8d, ecx
0x18003e2b7  add     eax, 4Eh ; 'N'
0x18003e2ba  lea     rcx, [rbp+var_20]
0x18003e2be  add     r8d, eax
0x18003e2c1  mov     rax, [rbp+arg_28]
0x18003e2c5  mov     [rax], r8d
0x18003e2c8  call    NlpAllocateClientBuffer
0x18003e2cd  mov     ebx, eax
0x18003e2cf  test    eax, eax
0x18003e2d1  js      short loc_18003E346
0x18003e2d3  mov     rbx, qword ptr [rbp+var_18+8]
0x18003e2d7  mov     r8d, esi; Size
0x18003e2da  mov     dword ptr [rbx], 3
0x18003e2e0  mov     eax, [rdi+38h]
0x18003e2e3  mov     [rbx+40h], eax
0x18003e2e6  mov     eax, dword ptr [rbp+var_8]
0x18003e2e9  add     rax, qword ptr [rbp+var_18]
0x18003e2ed  mov     [rbx+8], rax
0x18003e2f1  mov     ecx, dword ptr [rbp+var_8]
0x18003e2f4  add     rcx, qword ptr [rbp+var_18+8]; void *
0x18003e2f8  mov     rdx, [rdi+40h]; Src
0x18003e2fc  call    memcpy_0
0x18003e301  add     dword ptr [rbp+var_8], esi
0x18003e304  lea     rdx, [rbx+10h]
0x18003e308  lea     r8, [rdi+48h]
0x18003e30c  lea     rcx, [rbp+var_20]
0x18003e310  call    NlpPutClientString
0x18003e315  lea     rdx, [rbx+20h]
0x18003e319  lea     r8, [rdi+58h]
0x18003e31d  lea     rcx, [rbp+var_20]
0x18003e321  call    NlpPutClientString
0x18003e326  lea     rdx, [rbx+30h]
0x18003e32a  lea     r8, [rdi+68h]
0x18003e32e  lea     rcx, [rbp+var_20]
0x18003e332  call    NlpPutClientString
0x18003e337  mov     rdx, [rbp+arg_20]
0x18003e33b  lea     rcx, [rbp+var_20]
0x18003e33f  call    NlpFlushClientBuffer
0x18003e344  mov     ebx, eax
0x18003e346  lea     rcx, NlpActiveLogonLock; Resource
0x18003e34d  call    cs:__imp_RtlReleaseResource
0x18003e353  test    ebx, ebx
0x18003e355  jns     short loc_18003E360
0x18003e357  lea     rcx, [rbp+var_20]
0x18003e35b  call    NlpFreeClientBuffer
0x18003e360  mov     rax, [rbp+arg_30]
0x18003e364  mov     [rax], ebx
0x18003e366  xor     eax, eax
0x18003e368  add     rsp, 40h
0x18003e36c  pop     r15
0x18003e36e  pop     r14
0x18003e370  pop     r12
0x18003e372  pop     rdi
0x18003e373  pop     rsi
0x18003e374  pop     rbx
0x18003e375  pop     rbp
0x18003e376  retn
```
