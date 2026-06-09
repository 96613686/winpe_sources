# WSTAddTokenMessage(_WST_CONTEXT *,uchar *,ulong,_GUID *)

- ea: `0x1800011b4`
- end: `0x1800012d4`
- name: `?WSTAddTokenMessage@@YAJPEAU_WST_CONTEXT@@PEAEKPEAU_GUID@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(struct _WST_CONTEXT *, unsigned __int8 *, unsigned int, struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800070d0`
- `0x180008e60`
- `0x18001a3b4`

## callees

- `0x1800011b4`
- `0x1800027e4`
- `0x1800028a0`
- `0x18001ece2`

## pseudocode

```c
__int64 __fastcall WSTAddTokenMessage(struct _WST_CONTEXT *a1, unsigned __int8 *a2, unsigned int a3, struct _GUID *a4)
{
  size_t v4; // rbp
  unsigned int v8; // esi
  char *v9; // rax
  void *v10; // rbx
  unsigned int v11; // ecx
  int v12; // ecx
  _QWORD *v13; // rax
  struct _WST_CONTEXT **v14; // r8

  v4 = a3;
  v8 = a3 + 64;
  v9 = (char *)basessp::BaseSSP::WSTAllocate(WSTGlobalBaseSSP, a3 + 64);
  v10 = v9;
  if ( v9 )
  {
    *((_DWORD *)v9 + 4) = 64;
    *((_DWORD *)v9 + 5) = v8;
    *(_QWORD *)v9 = 0x535458454F47454ELL;
    v12 = *((_DWORD *)a1 + 35);
    *((_DWORD *)a1 + 35) = v12 + 1;
    *((_DWORD *)v9 + 3) = v12;
    *(_OWORD *)(v9 + 24) = *((_OWORD *)a1 + 2);
    *((_DWORD *)v9 + 2) = (*((_DWORD *)a1 + 39) != 0) + 4;
    *(struct _GUID *)(v9 + 40) = *a4;
    *((_DWORD *)v9 + 15) = v4;
    *((_DWORD *)v9 + 14) = 64;
    memcpy_0(v9 + 64, a2, v4);
    v13 = basessp::BaseSSP::WSTAllocate(WSTGlobalBaseSSP, 0x28u);
    if ( v13 )
    {
      v13[2] = 0x4547534D4F545357LL;
      v13[1] = v13;
      *v13 = v13;
      v13[3] = v10;
      *((_DWORD *)v13 + 8) = v8;
      v14 = (struct _WST_CONTEXT **)*((_QWORD *)a1 + 12);
      if ( *v14 != (struct _WST_CONTEXT *)((char *)a1 + 88) )
        __fastfail(3u);
      *v13 = (char *)a1 + 88;
      v11 = 0;
      v13[1] = v14;
      *v14 = (struct _WST_CONTEXT *)v13;
      *((_QWORD *)a1 + 12) = v13;
      if ( *((int *)a1 + 12) < 3 )
        *((_DWORD *)a1 + 12) = 3;
    }
    else
    {
      WSTFree(v10);
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return v11;
}

```

## disassembly

```asm
0x1800011b4  push    rbx
0x1800011b6  push    rbp
0x1800011b7  push    rsi
0x1800011b8  push    rdi
0x1800011b9  push    r14
0x1800011bb  push    r15
0x1800011bd  sub     rsp, 28h
0x1800011c1  mov     ebp, r8d
0x1800011c4  mov     r15, rdx
0x1800011c7  mov     rdi, rcx
0x1800011ca  mov     r14, r9
0x1800011cd  mov     rcx, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x1800011d4  lea     esi, [rbp+40h]
0x1800011d7  mov     edx, esi; unsigned __int64
0x1800011d9  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x1800011de  mov     rbx, rax
0x1800011e1  test    rax, rax
0x1800011e4  jnz     short loc_1800011F0
0x1800011e6  mov     ecx, 0C0000017h
0x1800011eb  jmp     loc_1800012C5
0x1800011f0  mov     edx, 40h ; '@'
0x1800011f5  mov     r8, rbp; Size
0x1800011f8  mov     [rax+10h], edx
0x1800011fb  mov     [rax+14h], esi
0x1800011fe  mov     rax, 535458454F47454Eh
0x180001208  mov     [rbx], rax
0x18000120b  mov     ecx, [rdi+8Ch]
0x180001211  lea     eax, [rcx+1]
0x180001214  mov     [rdi+8Ch], eax
0x18000121a  mov     [rbx+0Ch], ecx
0x18000121d  movups  xmm0, xmmword ptr [rdi+20h]
0x180001221  movdqu  xmmword ptr [rbx+18h], xmm0
0x180001226  mov     eax, [rdi+9Ch]
0x18000122c  neg     eax
0x18000122e  sbb     ecx, ecx
0x180001230  neg     ecx
0x180001232  add     ecx, 4
0x180001235  mov     [rbx+8], ecx
0x180001238  lea     rcx, [rbx+40h]; void *
0x18000123c  movups  xmm0, xmmword ptr [r14]
0x180001240  movdqu  xmmword ptr [rbx+28h], xmm0
0x180001245  mov     [rbx+3Ch], ebp
0x180001248  mov     [rbx+38h], edx
0x18000124b  mov     rdx, r15; Src
0x18000124e  call    memcpy_0
0x180001253  mov     rcx, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18000125a  mov     edx, 28h ; '('; unsigned __int64
0x18000125f  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180001264  test    rax, rax
0x180001267  jz      short loc_1800012B8
0x180001269  mov     rcx, 4547534D4F545357h
0x180001273  mov     [rax+10h], rcx
0x180001277  mov     [rax+8], rax
0x18000127b  mov     [rax], rax
0x18000127e  mov     [rax+18h], rbx
0x180001282  mov     [rax+20h], esi
0x180001285  lea     rdx, [rdi+58h]
0x180001289  mov     r8, [rdx+8]
0x18000128d  cmp     [r8], rdx
0x180001290  jz      short loc_180001299
0x180001292  mov     ecx, 3
0x180001297  int     29h; Win8: RtlFailFast(ecx)
0x180001299  mov     [rax], rdx
0x18000129c  xor     ecx, ecx
0x18000129e  mov     [rax+8], r8
0x1800012a2  mov     [r8], rax
0x1800012a5  mov     [rdx+8], rax
0x1800012a9  cmp     dword ptr [rdi+30h], 3
0x1800012ad  jge     short loc_1800012C5
0x1800012af  mov     dword ptr [rdi+30h], 3
0x1800012b6  jmp     short loc_1800012C5
0x1800012b8  mov     rcx, rbx; void *
0x1800012bb  call    ?WSTFree@@YAXPEAX@Z; WSTFree(void *)
0x1800012c0  mov     ecx, 0C000009Ah
0x1800012c5  mov     eax, ecx
0x1800012c7  add     rsp, 28h
0x1800012cb  pop     r15
0x1800012cd  pop     r14
0x1800012cf  pop     rdi
0x1800012d0  pop     rsi
0x1800012d1  pop     rbp
0x1800012d2  pop     rbx
0x1800012d3  retn
```
