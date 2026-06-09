# TMetabaseMetaXmlFile::AddShippedIndexMetaToHeap(ulong,IndexMeta const *)

- ea: `0x18001a914`
- end: `0x18001aabb`
- name: `?AddShippedIndexMetaToHeap@TMetabaseMetaXmlFile@@AEAAXKPEBUIndexMeta@@@Z`
- size: `423`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this, unsigned int, const struct IndexMeta *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001aac4`

## callees

- `0x18001a914`
- `0x18002e110`
- `0x180030010`

## pseudocode

```c
void __fastcall TMetabaseMetaXmlFile::AddShippedIndexMetaToHeap(
        TMetabaseMetaXmlFile *this,
        int a2,
        const struct IndexMeta *a3)
{
  bool v3; // zf
  __int64 v4; // rax
  __int64 (__fastcall *v7)(TMetabaseMetaXmlFile *, __int64, __int64); // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  unsigned int *v17; // rdx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rax
  int v23; // eax
  unsigned int *v24; // rdx
  int v25; // [rsp+20h] [rbp-38h] BYREF
  __int128 v26; // [rsp+24h] [rbp-34h]
  __int64 v27; // [rsp+34h] [rbp-24h]

  v3 = *((_DWORD *)a3 + 1) == 0;
  v4 = *(_QWORD *)this;
  v27 = 0;
  v26 = 0;
  v25 = a2;
  v7 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(v4 + 40);
  if ( v3 )
  {
    v11 = 0;
    v10 = 0;
  }
  else
  {
    v8 = *((_QWORD *)this + 323);
    v9 = *((unsigned int *)a3 + 1);
    v10 = *(_DWORD *)(v9 + *(unsigned int *)(v8 + 56) + v8 - 4) >> 1;
    v11 = v8 + v9 + *(unsigned int *)(v8 + 56);
  }
  v12 = v7(this, v11, v10);
  v13 = *((unsigned int *)a3 + 2);
  LODWORD(v26) = v12;
  if ( (_DWORD)v13 != *((_DWORD *)a3 + 1) )
  {
    if ( (_DWORD)v13 )
    {
      v14 = *((_QWORD *)this + 323);
      v15 = *(_DWORD *)(v13 + *(unsigned int *)(v14 + 56) + v14 - 4) >> 1;
      v16 = v14 + v13 + *(unsigned int *)(v14 + 56);
    }
    else
    {
      v16 = 0;
      v15 = 0;
    }
    v12 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(*(_QWORD *)this + 40LL))(this, v16, v15);
  }
  v3 = *((_DWORD *)a3 + 3) == 0;
  DWORD1(v26) = v12;
  if ( v3 )
    v17 = 0;
  else
    v17 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a3 + 3));
  v18 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v17);
  v3 = *((_DWORD *)a3 + 4) == 0;
  DWORD2(v26) = v18;
  if ( v3 )
  {
    v22 = 0;
    v21 = 0;
  }
  else
  {
    v19 = *((_QWORD *)this + 323);
    v20 = *((unsigned int *)a3 + 4);
    v21 = *(_DWORD *)(v20 + *(unsigned int *)(v19 + 56) + v19 - 4) >> 1;
    v22 = v19 + v20 + *(unsigned int *)(v19 + 56);
  }
  v23 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(*(_QWORD *)this + 40LL))(this, v22, v21);
  v3 = *((_DWORD *)a3 + 5) == 0;
  HIDWORD(v26) = v23;
  if ( v3 )
    v24 = 0;
  else
    v24 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a3 + 5));
  LODWORD(v27) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v24);
  (*(void (__fastcall **)(TMetabaseMetaXmlFile *, int *, __int64))(*(_QWORD *)this + 80LL))(this, &v25, 1);
}

```

## disassembly

```asm
0x18001a914  mov     [rsp+arg_18], rbx
0x18001a919  push    rdi
0x18001a91a  sub     rsp, 50h
0x18001a91e  mov     rax, cs:__security_cookie
0x18001a925  xor     rax, rsp
0x18001a928  mov     [rsp+58h+var_18], rax
0x18001a92d  cmp     dword ptr [r8+4], 0
0x18001a932  xorps   xmm0, xmm0
0x18001a935  mov     rax, [rcx]
0x18001a938  mov     rdi, r8
0x18001a93b  mov     rbx, rcx
0x18001a93e  mov     [rsp+58h+var_24], 0
0x18001a947  movdqu  [rsp+58h+var_34], xmm0
0x18001a94d  mov     [rsp+58h+var_38], edx
0x18001a951  mov     r9, [rax+28h]
0x18001a955  jz      short loc_18001A97B
0x18001a957  mov     rdx, [rcx+0A18h]
0x18001a95e  mov     ecx, [r8+4]
0x18001a962  mov     eax, [rdx+38h]
0x18001a965  add     rax, rcx
0x18001a968  mov     r8d, [rax+rdx-4]
0x18001a96d  mov     eax, [rdx+38h]
0x18001a970  add     rax, rcx
0x18001a973  shr     r8d, 1
0x18001a976  add     rax, rdx
0x18001a979  jmp     short loc_18001A980
0x18001a97b  xor     eax, eax
0x18001a97d  xor     r8d, r8d
0x18001a980  mov     rdx, rax
0x18001a983  mov     rcx, rbx
0x18001a986  mov     rax, r9
0x18001a989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a98e  mov     ecx, [rdi+8]
0x18001a991  mov     dword ptr [rsp+58h+var_34], eax
0x18001a995  cmp     ecx, [rdi+4]
0x18001a998  jz      short loc_18001A9D8
0x18001a99a  mov     rax, [rbx]
0x18001a99d  mov     r9, [rax+28h]
0x18001a9a1  test    ecx, ecx
0x18001a9a3  jz      short loc_18001A9C5
0x18001a9a5  mov     rdx, [rbx+0A18h]
0x18001a9ac  mov     eax, [rdx+38h]
0x18001a9af  add     rax, rcx
0x18001a9b2  mov     r8d, [rax+rdx-4]
0x18001a9b7  mov     eax, [rdx+38h]
0x18001a9ba  add     rax, rcx
0x18001a9bd  shr     r8d, 1
0x18001a9c0  add     rax, rdx
0x18001a9c3  jmp     short loc_18001A9CA
0x18001a9c5  xor     eax, eax
0x18001a9c7  xor     r8d, r8d
0x18001a9ca  mov     rdx, rax
0x18001a9cd  mov     rcx, rbx
0x18001a9d0  mov     rax, r9
0x18001a9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9d8  cmp     dword ptr [rdi+0Ch], 0
0x18001a9dc  mov     dword ptr [rsp+58h+var_34+4], eax
0x18001a9e0  mov     rax, [rbx]
0x18001a9e3  jnz     short loc_18001A9E9
0x18001a9e5  xor     edx, edx
0x18001a9e7  jmp     short loc_18001A9FD
0x18001a9e9  mov     r8, [rbx+0A18h]
0x18001a9f0  mov     edx, [rdi+0Ch]
0x18001a9f3  mov     ecx, [r8+38h]
0x18001a9f7  add     rcx, r8
0x18001a9fa  add     rdx, rcx
0x18001a9fd  mov     edx, [rdx]
0x18001a9ff  mov     rcx, rbx
0x18001aa02  mov     rax, [rax+10h]
0x18001aa06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa0b  cmp     dword ptr [rdi+10h], 0
0x18001aa0f  mov     dword ptr [rsp+58h+var_34+8], eax
0x18001aa13  mov     rax, [rbx]
0x18001aa16  mov     r9, [rax+28h]
0x18001aa1a  jz      short loc_18001AA3F
0x18001aa1c  mov     rdx, [rbx+0A18h]
0x18001aa23  mov     ecx, [rdi+10h]
0x18001aa26  mov     eax, [rdx+38h]
0x18001aa29  add     rax, rcx
0x18001aa2c  mov     r8d, [rax+rdx-4]
0x18001aa31  mov     eax, [rdx+38h]
0x18001aa34  add     rax, rcx
0x18001aa37  shr     r8d, 1
0x18001aa3a  add     rax, rdx
0x18001aa3d  jmp     short loc_18001AA44
0x18001aa3f  xor     eax, eax
0x18001aa41  xor     r8d, r8d
0x18001aa44  mov     rdx, rax
0x18001aa47  mov     rcx, rbx
0x18001aa4a  mov     rax, r9
0x18001aa4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa52  cmp     dword ptr [rdi+14h], 0
0x18001aa56  mov     dword ptr [rsp+58h+var_34+0Ch], eax
0x18001aa5a  mov     rax, [rbx]
0x18001aa5d  jnz     short loc_18001AA63
0x18001aa5f  xor     edx, edx
0x18001aa61  jmp     short loc_18001AA77
0x18001aa63  mov     r8, [rbx+0A18h]
0x18001aa6a  mov     edx, [rdi+14h]
0x18001aa6d  mov     ecx, [r8+38h]
0x18001aa71  add     rcx, r8
0x18001aa74  add     rdx, rcx
0x18001aa77  mov     edx, [rdx]
0x18001aa79  mov     rcx, rbx
0x18001aa7c  mov     rax, [rax+10h]
0x18001aa80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa85  mov     dword ptr [rsp+58h+var_24], eax
0x18001aa89  lea     rdx, [rsp+58h+var_38]
0x18001aa8e  mov     rax, [rbx]
0x18001aa91  mov     r8d, 1
0x18001aa97  mov     rcx, rbx
0x18001aa9a  mov     rax, [rax+50h]
0x18001aa9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaa3  mov     rcx, [rsp+58h+var_18]
0x18001aaa8  xor     rcx, rsp; StackCookie
0x18001aaab  call    __security_check_cookie
0x18001aab0  mov     rbx, [rsp+58h+arg_18]
0x18001aab5  add     rsp, 50h
0x18001aab9  pop     rdi
0x18001aaba  retn
```
