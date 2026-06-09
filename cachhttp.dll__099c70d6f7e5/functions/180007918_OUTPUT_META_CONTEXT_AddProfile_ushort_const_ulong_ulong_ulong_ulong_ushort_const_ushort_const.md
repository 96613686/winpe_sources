# OUTPUT_META_CONTEXT::AddProfile(ushort const *,ulong,ulong,ulong,ulong,ushort const *,ushort const *)

- ea: `0x180007918`
- end: `0x180007ad1`
- name: `?AddProfile@OUTPUT_META_CONTEXT@@AEAAJPEBGKKKK00@Z`
- size: `441`
- prototype: `__int64 __fastcall(OUTPUT_META_CONTEXT *this, const unsigned __int16 *, int, int, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002a4c`

## callees

- `0x180005a0c`
- `0x1800078b4`
- `0x180007918`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180007950`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007950`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800079b5`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800079b5`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJPEBG@Z` at `0x1800079d4`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJPEBG@Z` at `0x1800079d4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007999`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007999`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000795a`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180007967`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000795a`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180007967`

## pseudocode

```c
__int64 __fastcall OUTPUT_META_CONTEXT::AddProfile(
        OUTPUT_META_CONTEXT *this,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8)
{
  char *v12; // rax
  _QWORD *v13; // rbx
  unsigned int v14; // edx
  int v15; // ebp
  int v16; // esi
  int v17; // esi
  int v18; // edi
  int v19; // edi
  OUTPUT_META_CONTEXT **v20; // rcx

  v12 = (char *)operator new(0xD0u);
  v13 = v12;
  if ( !v12 )
    return 2147942408LL;
  STRU::STRU((STRU *)(v12 + 16));
  STRA::STRA((STRA *)(v13 + 9));
  STRA::STRA((STRA *)(v13 + 16));
  v13[1] = v13;
  *v13 = v13;
  *((_DWORD *)v13 + 46) = 0;
  *((_DWORD *)v13 + 48) = 0;
  *((_WORD *)v13 + 100) = 257;
  *((_DWORD *)v13 + 51) = 0;
  v15 = STRU::Copy((STRU *)(v13 + 2), a2);
  if ( v15 < 0
    || (v15 = STRA::CopyW((STRA *)(v13 + 9), a7), v15 < 0)
    || (v15 = STRA::CopyWToUTF8Escaped((STRA *)(v13 + 16), a8), v15 < 0) )
  {
    CACHING_PROFILE::`scalar deleting destructor'((CACHING_PROFILE *)v13, v14);
    return (unsigned int)v15;
  }
  else
  {
    if ( a3 )
    {
      v16 = a3 - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          if ( v17 == 1 )
            *((_BYTE *)v13 + 200) = 0;
        }
        else
        {
          *((_DWORD *)v13 + 46) = 2;
          *((_DWORD *)v13 + 47) = a5;
        }
      }
      else
      {
        *((_DWORD *)v13 + 46) = 1;
      }
    }
    else
    {
      *((_DWORD *)v13 + 46) = 0;
    }
    if ( a4 )
    {
      v18 = a4 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          if ( v19 == 1 )
            *((_BYTE *)v13 + 201) = 0;
        }
        else
        {
          *((_DWORD *)v13 + 48) = 2;
          *((_DWORD *)v13 + 49) = a5;
        }
      }
      else
      {
        *((_DWORD *)v13 + 48) = 1;
      }
    }
    else
    {
      *((_DWORD *)v13 + 48) = 0;
    }
    *((_DWORD *)v13 + 51) = a6;
    if ( *a2 != 42 || a2[1] )
    {
      v20 = (OUTPUT_META_CONTEXT **)*((_QWORD *)this + 3);
      if ( *v20 != (OUTPUT_META_CONTEXT *)((char *)this + 16) )
        __fastfail(3u);
      *v13 = (char *)this + 16;
      v13[1] = v20;
      *v20 = (OUTPUT_META_CONTEXT *)v13;
      *((_QWORD *)this + 3) = v13;
    }
    else
    {
      *((_QWORD *)this + 4) = v13;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180007918  push    rbx
0x18000791a  push    rbp
0x18000791b  push    rsi
0x18000791c  push    rdi
0x18000791d  push    r12
0x18000791f  push    r14
0x180007921  push    r15
0x180007923  sub     rsp, 20h
0x180007927  mov     r15, rcx
0x18000792a  mov     edi, r9d
0x18000792d  mov     ecx, 0D0h; Size
0x180007932  mov     esi, r8d
0x180007935  mov     r14, rdx
0x180007938  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000793d  xor     r12d, r12d
0x180007940  mov     rbx, rax
0x180007943  test    rax, rax
0x180007946  jz      loc_180007ABD
0x18000794c  lea     rcx, [rax+10h]
0x180007950  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180007956  lea     rcx, [rbx+48h]
0x18000795a  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180007960  lea     rcx, [rbx+80h]
0x180007967  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000796d  mov     [rbx+8], rbx
0x180007971  lea     rcx, [rbx+10h]
0x180007975  mov     [rbx], rbx
0x180007978  mov     rdx, r14
0x18000797b  mov     [rbx+0B8h], r12d
0x180007982  mov     [rbx+0C0h], r12d
0x180007989  mov     word ptr [rbx+0C8h], 101h
0x180007992  mov     [rbx+0CCh], r12d
0x180007999  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000799f  mov     ebp, eax
0x1800079a1  test    eax, eax
0x1800079a3  js      loc_180007AB1
0x1800079a9  mov     rdx, [rsp+58h+arg_30]
0x1800079b1  lea     rcx, [rbx+48h]
0x1800079b5  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x1800079bb  mov     ebp, eax
0x1800079bd  test    eax, eax
0x1800079bf  js      loc_180007AB1
0x1800079c5  mov     rdx, [rsp+58h+arg_38]
0x1800079cd  lea     rcx, [rbx+80h]
0x1800079d4  call    cs:__imp_?CopyWToUTF8Escaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Escaped(ushort const *)
0x1800079da  mov     ebp, eax
0x1800079dc  test    eax, eax
0x1800079de  js      loc_180007AB1
0x1800079e4  mov     eax, [rsp+58h+arg_20]
0x1800079eb  lea     ecx, [r12+2]
0x1800079f0  test    esi, esi
0x1800079f2  jz      short loc_180007A26
0x1800079f4  sub     esi, 1
0x1800079f7  jz      short loc_180007A1A
0x1800079f9  sub     esi, 1
0x1800079fc  jz      short loc_180007A0C
0x1800079fe  cmp     esi, 1
0x180007a01  jnz     short loc_180007A2D
0x180007a03  mov     [rbx+0C8h], r12b
0x180007a0a  jmp     short loc_180007A2D
0x180007a0c  mov     [rbx+0B8h], ecx
0x180007a12  mov     [rbx+0BCh], eax
0x180007a18  jmp     short loc_180007A2D
0x180007a1a  mov     dword ptr [rbx+0B8h], 1
0x180007a24  jmp     short loc_180007A2D
0x180007a26  mov     [rbx+0B8h], r12d
0x180007a2d  test    edi, edi
0x180007a2f  jz      short loc_180007A63
0x180007a31  sub     edi, 1
0x180007a34  jz      short loc_180007A57
0x180007a36  sub     edi, 1
0x180007a39  jz      short loc_180007A49
0x180007a3b  cmp     edi, 1
0x180007a3e  jnz     short loc_180007A6A
0x180007a40  mov     [rbx+0C9h], r12b
0x180007a47  jmp     short loc_180007A6A
0x180007a49  mov     [rbx+0C0h], ecx
0x180007a4f  mov     [rbx+0C4h], eax
0x180007a55  jmp     short loc_180007A6A
0x180007a57  mov     dword ptr [rbx+0C0h], 1
0x180007a61  jmp     short loc_180007A6A
0x180007a63  mov     [rbx+0C0h], r12d
0x180007a6a  mov     eax, [rsp+58h+arg_28]
0x180007a71  mov     [rbx+0CCh], eax
0x180007a77  cmp     word ptr [r14], 2Ah ; '*'
0x180007a7c  jnz     short loc_180007A8B
0x180007a7e  cmp     [r14+2], r12w
0x180007a83  jnz     short loc_180007A8B
0x180007a85  mov     [r15+20h], rbx
0x180007a89  jmp     short loc_180007AAD
0x180007a8b  lea     rax, [r15+10h]
0x180007a8f  mov     rcx, [rax+8]
0x180007a93  cmp     [rcx], rax
0x180007a96  jz      short loc_180007A9F
0x180007a98  mov     ecx, 3
0x180007a9d  int     29h; Win8: RtlFailFast(ecx)
0x180007a9f  mov     [rbx], rax
0x180007aa2  mov     [rbx+8], rcx
0x180007aa6  mov     [rcx], rbx
0x180007aa9  mov     [rax+8], rbx
0x180007aad  xor     eax, eax
0x180007aaf  jmp     short loc_180007AC2
0x180007ab1  mov     rcx, rbx; this
0x180007ab4  call    ??_GCACHING_PROFILE@@QEAAPEAXI@Z; CACHING_PROFILE::`scalar deleting destructor'(uint)
0x180007ab9  mov     eax, ebp
0x180007abb  jmp     short loc_180007AC2
0x180007abd  mov     eax, 80070008h
0x180007ac2  add     rsp, 20h
0x180007ac6  pop     r15
0x180007ac8  pop     r14
0x180007aca  pop     r12
0x180007acc  pop     rdi
0x180007acd  pop     rsi
0x180007ace  pop     rbp
0x180007acf  pop     rbx
0x180007ad0  retn
```
