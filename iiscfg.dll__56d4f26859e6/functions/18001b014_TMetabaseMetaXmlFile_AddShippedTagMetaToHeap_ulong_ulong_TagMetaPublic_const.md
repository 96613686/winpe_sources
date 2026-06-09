# TMetabaseMetaXmlFile::AddShippedTagMetaToHeap(ulong,ulong,TagMetaPublic const *)

- ea: `0x18001b014`
- end: `0x18001b180`
- name: `?AddShippedTagMetaToHeap@TMetabaseMetaXmlFile@@AEAAXKKPEBUTagMetaPublic@@@Z`
- size: `364`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this, unsigned int, unsigned int, const struct TagMetaPublic *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001a444`

## callees

- `0x18001b014`
- `0x18002e110`
- `0x180030010`

## pseudocode

```c
void __fastcall TMetabaseMetaXmlFile::AddShippedTagMetaToHeap(
        TMetabaseMetaXmlFile *this,
        int a2,
        int a3,
        const struct TagMetaPublic *a4)
{
  __int64 v4; // rax
  bool v7; // zf
  __int64 (__fastcall *v8)(TMetabaseMetaXmlFile *, __int64, __int64); // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  unsigned int *v18; // rdx
  int v19; // eax
  unsigned int *v20; // rdx
  _DWORD v21[2]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v22; // [rsp+28h] [rbp-30h]

  v4 = *(_QWORD *)this;
  v21[0] = a2;
  v21[1] = a3;
  v22 = 0;
  v7 = *((_DWORD *)a4 + 2) == 0;
  v8 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(v4 + 40);
  if ( v7 )
  {
    v12 = 0;
    v11 = 0;
  }
  else
  {
    v9 = *((_QWORD *)this + 323);
    v10 = *((unsigned int *)a4 + 2);
    v11 = *(_DWORD *)(v10 + *(unsigned int *)(v9 + 56) + v9 - 4) >> 1;
    v12 = v9 + v10 + *(unsigned int *)(v9 + 56);
  }
  v13 = v8(this, v12, v11);
  v14 = *((unsigned int *)a4 + 3);
  LODWORD(v22) = v13;
  if ( (_DWORD)v14 != *((_DWORD *)a4 + 2) )
  {
    if ( (_DWORD)v14 )
    {
      v15 = *((_QWORD *)this + 323);
      v16 = *(_DWORD *)(v14 + *(unsigned int *)(v15 + 56) + v15 - 4) >> 1;
      v17 = v15 + v14 + *(unsigned int *)(v15 + 56);
    }
    else
    {
      v17 = 0;
      v16 = 0;
    }
    v13 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(*(_QWORD *)this + 40LL))(this, v17, v16);
  }
  v7 = *((_DWORD *)a4 + 4) == 0;
  DWORD1(v22) = v13;
  if ( v7 )
    v18 = 0;
  else
    v18 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a4 + 4));
  v19 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v18);
  v7 = *((_DWORD *)a4 + 5) == 0;
  DWORD2(v22) = v19;
  if ( v7 )
    v20 = 0;
  else
    v20 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a4 + 5));
  HIDWORD(v22) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v20);
  *((_DWORD *)this + 641) = (*(unsigned int (__fastcall **)(TMetabaseMetaXmlFile *, _DWORD *, __int64))(*(_QWORD *)this + 120LL))(
                              this,
                              v21,
                              1)
                          / 0x18;
}

```

## disassembly

```asm
0x18001b014  push    rbx
0x18001b016  push    rdi
0x18001b017  sub     rsp, 48h
0x18001b01b  mov     rax, cs:__security_cookie
0x18001b022  xor     rax, rsp
0x18001b025  mov     [rsp+58h+var_20], rax
0x18001b02a  mov     rax, [rcx]
0x18001b02d  mov     rdi, r9
0x18001b030  xorps   xmm0, xmm0
0x18001b033  mov     [rsp+58h+var_38], edx
0x18001b037  mov     rbx, rcx
0x18001b03a  mov     [rsp+58h+var_34], r8d
0x18001b03f  movdqu  [rsp+58h+var_30], xmm0
0x18001b045  cmp     dword ptr [rdi+8], 0
0x18001b049  mov     r9, [rax+28h]
0x18001b04d  jz      short loc_18001B072
0x18001b04f  mov     rdx, [rcx+0A18h]
0x18001b056  mov     ecx, [rdi+8]
0x18001b059  mov     eax, [rdx+38h]
0x18001b05c  add     rax, rcx
0x18001b05f  mov     r8d, [rax+rdx-4]
0x18001b064  mov     eax, [rdx+38h]
0x18001b067  add     rax, rcx
0x18001b06a  shr     r8d, 1
0x18001b06d  add     rax, rdx
0x18001b070  jmp     short loc_18001B077
0x18001b072  xor     eax, eax
0x18001b074  xor     r8d, r8d
0x18001b077  mov     rdx, rax
0x18001b07a  mov     rcx, rbx
0x18001b07d  mov     rax, r9
0x18001b080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b085  mov     ecx, [rdi+0Ch]
0x18001b088  mov     dword ptr [rsp+58h+var_30], eax
0x18001b08c  cmp     ecx, [rdi+8]
0x18001b08f  jz      short loc_18001B0CF
0x18001b091  mov     rax, [rbx]
0x18001b094  mov     r9, [rax+28h]
0x18001b098  test    ecx, ecx
0x18001b09a  jz      short loc_18001B0BC
0x18001b09c  mov     rdx, [rbx+0A18h]
0x18001b0a3  mov     eax, [rdx+38h]
0x18001b0a6  add     rax, rcx
0x18001b0a9  mov     r8d, [rax+rdx-4]
0x18001b0ae  mov     eax, [rdx+38h]
0x18001b0b1  add     rax, rcx
0x18001b0b4  shr     r8d, 1
0x18001b0b7  add     rax, rdx
0x18001b0ba  jmp     short loc_18001B0C1
0x18001b0bc  xor     eax, eax
0x18001b0be  xor     r8d, r8d
0x18001b0c1  mov     rdx, rax
0x18001b0c4  mov     rcx, rbx
0x18001b0c7  mov     rax, r9
0x18001b0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0cf  cmp     dword ptr [rdi+10h], 0
0x18001b0d3  mov     dword ptr [rsp+58h+var_30+4], eax
0x18001b0d7  mov     rax, [rbx]
0x18001b0da  jnz     short loc_18001B0E0
0x18001b0dc  xor     edx, edx
0x18001b0de  jmp     short loc_18001B0F4
0x18001b0e0  mov     r8, [rbx+0A18h]
0x18001b0e7  mov     edx, [rdi+10h]
0x18001b0ea  mov     ecx, [r8+38h]
0x18001b0ee  add     rcx, r8
0x18001b0f1  add     rdx, rcx
0x18001b0f4  mov     edx, [rdx]
0x18001b0f6  mov     rcx, rbx
0x18001b0f9  mov     rax, [rax+10h]
0x18001b0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b102  cmp     dword ptr [rdi+14h], 0
0x18001b106  mov     dword ptr [rsp+58h+var_30+8], eax
0x18001b10a  mov     rax, [rbx]
0x18001b10d  jnz     short loc_18001B113
0x18001b10f  xor     edx, edx
0x18001b111  jmp     short loc_18001B127
0x18001b113  mov     r8, [rbx+0A18h]
0x18001b11a  mov     edx, [rdi+14h]
0x18001b11d  mov     ecx, [r8+38h]
0x18001b121  add     rcx, r8
0x18001b124  add     rdx, rcx
0x18001b127  mov     edx, [rdx]
0x18001b129  mov     rcx, rbx
0x18001b12c  mov     rax, [rax+10h]
0x18001b130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b135  mov     dword ptr [rsp+58h+var_30+0Ch], eax
0x18001b139  lea     rdx, [rsp+58h+var_38]
0x18001b13e  mov     rax, [rbx]
0x18001b141  mov     r8d, 1
0x18001b147  mov     rcx, rbx
0x18001b14a  mov     rax, [rax+78h]
0x18001b14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b153  mov     ecx, eax
0x18001b155  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001b15f  mul     rcx
0x18001b162  shr     rdx, 4
0x18001b166  mov     [rbx+0A04h], edx
0x18001b16c  mov     rcx, [rsp+58h+var_20]
0x18001b171  xor     rcx, rsp; StackCookie
0x18001b174  call    __security_check_cookie
0x18001b179  add     rsp, 48h
0x18001b17d  pop     rdi
0x18001b17e  pop     rbx
0x18001b17f  retn
```
