# ResourceHolder::GetProviderGuidsEx(wchar_t const *,wchar_t const *,wchar_t const *,ulong,_GUID *,ulong *)

- ea: `0x18002b9d0`
- end: `0x18002bb5f`
- name: `?GetProviderGuidsEx@ResourceHolder@@QEAAKPEB_W00KPEAU_GUID@@PEAK@Z`
- size: `399`
- prototype: `unsigned int __usercall@<eax>(ResourceHolder *__hidden this@<rcx>, const wchar_t *@<rdx>, const wchar_t *@<r8>, const wchar_t *@<r9>, unsigned int, struct _GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180025ed8`

## callees

- `0x18000777c`
- `0x18000799c`
- `0x180007c48`
- `0x18002b9d0`

## string_xrefs

- `0x18002b9f2`: `WEVT_TEMPLATE`

## pseudocode

```c
__int64 __fastcall ResourceHolder::GetProviderGuidsEx(
        struct _GUID **this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        unsigned int a5,
        struct _GUID *a6,
        unsigned int *a7)
{
  unsigned int v8; // ebx
  struct _GUID *v9; // rcx
  unsigned __int64 v10; // r15
  unsigned int v11; // r11d
  struct _GUID *v12; // r14
  unsigned __int64 v13; // r10
  unsigned int i; // esi
  struct _GUID *v15; // rbx
  __int64 v16; // rax
  const struct ProviderWrapper *v17; // rdx
  unsigned int v18; // r10d
  const struct ProviderWrapper *v19; // rdx
  int v20; // r10d
  int v21; // r11d
  bool v23; // [rsp+20h] [rbp-48h]

  if ( this[5]
    || (v8 = ResourceHolder::LoadAndValidateGlobalResource((ResourceHolder *)this, a2, L"#1", L"WEVT_TEMPLATE", v23)) == 0 )
  {
    v9 = *this;
    v10 = (unsigned __int64)*this + *((unsigned int *)this + 6);
    if ( v10 < (unsigned __int64)*this )
    {
      v8 = 13;
    }
    else
    {
      v11 = 0;
      v12 = v9 + 1;
      v13 = (unsigned __int64)&v9[1];
      for ( i = 0; ; ++i )
      {
        v15 = this[1];
        if ( i >= *(_DWORD *)&v15->Data4[4] )
          break;
        if ( v13 > (unsigned __int64)*this && v13 < v10 && v13 + 20 >= v13 && v13 + 20 <= v10 )
        {
          v16 = *(unsigned int *)(v13 + 16);
          if ( (int)v16 + 16 >= (unsigned int)v16 && (unsigned int)(v16 + 16) <= *((_DWORD *)this + 6) )
          {
            v17 = (const struct ProviderWrapper *)((char *)*this + v16);
            this[2] = (struct _GUID *)v17;
            if ( !ResourceHolder::ValidateProviderEntry((ResourceHolder *)this, v17, v10) )
              ++v11;
          }
        }
        v13 += 20LL;
      }
      *a7 = v11;
      if ( a5 >= v11 )
      {
        v18 = 0;
        while ( v18 < *(_DWORD *)&v15->Data4[4] )
        {
          v19 = (const struct ProviderWrapper *)((char *)*this + v12[1].Data1);
          this[2] = (struct _GUID *)v19;
          if ( !ResourceHolder::ValidateProviderEntry((ResourceHolder *)this, v19, v10) )
          {
            a6[v21] = *v12;
            v15 = this[1];
          }
          v18 = v20 + 1;
          v12 = (struct _GUID *)((char *)v12 + 20);
        }
        v8 = 0;
      }
      else
      {
        v8 = 122;
      }
    }
  }
  ResourceHolder::Close((ResourceHolder *)this);
  return v8;
}

```

## disassembly

```asm
0x18002b9d0  mov     [rsp+arg_8], rbx
0x18002b9d5  mov     [rsp+arg_10], rsi
0x18002b9da  mov     [rsp+arg_0], rcx
0x18002b9df  push    rdi
0x18002b9e0  push    r14
0x18002b9e2  push    r15
0x18002b9e4  sub     rsp, 50h
0x18002b9e8  mov     rdi, rcx
0x18002b9eb  cmp     qword ptr [rcx+28h], 0
0x18002b9f0  jnz     short loc_18002BA13
0x18002b9f2  lea     r9, aWevtTemplate; "WEVT_TEMPLATE"
0x18002b9f9  lea     r8, a1; "#1"
0x18002ba00  call    ?LoadAndValidateGlobalResource@ResourceHolder@@QEAAKPEB_W00_N@Z; ResourceHolder::LoadAndValidateGlobalResource(wchar_t const *,wchar_t const *,wchar_t const *,bool)
0x18002ba05  mov     ebx, eax
0x18002ba07  mov     [rsp+68h+var_34], eax
0x18002ba0b  test    eax, eax
0x18002ba0d  jnz     loc_18002BB3F
0x18002ba13  mov     rcx, [rdi]
0x18002ba16  mov     r15d, [rdi+18h]
0x18002ba1a  add     r15, rcx
0x18002ba1d  cmp     r15, rcx
0x18002ba20  jb      loc_18002BB26
0x18002ba26  xor     r11d, r11d
0x18002ba29  mov     [rsp+68h+var_38], r11d
0x18002ba2e  lea     r14, [rcx+10h]
0x18002ba32  mov     r10, r14
0x18002ba35  mov     [rsp+68h+var_28], r14
0x18002ba3a  xor     esi, esi
0x18002ba3c  mov     [rsp+68h+var_30], esi
0x18002ba40  mov     rbx, [rdi+8]
0x18002ba44  cmp     esi, [rbx+0Ch]
0x18002ba47  jnb     short loc_18002BAA1
0x18002ba49  mov     rdx, [rdi]
0x18002ba4c  cmp     r10, rdx
0x18002ba4f  jbe     short loc_18002BA94
0x18002ba51  cmp     r10, r15
0x18002ba54  jnb     short loc_18002BA94
0x18002ba56  lea     rax, [r10+14h]
0x18002ba5a  cmp     rax, r10
0x18002ba5d  jb      short loc_18002BA94
0x18002ba5f  cmp     rax, r15
0x18002ba62  ja      short loc_18002BA94
0x18002ba64  mov     eax, [r10+10h]
0x18002ba68  lea     ecx, [rax+10h]
0x18002ba6b  cmp     ecx, eax
0x18002ba6d  jb      short loc_18002BA94
0x18002ba6f  cmp     ecx, [rdi+18h]
0x18002ba72  ja      short loc_18002BA94
0x18002ba74  add     rdx, rax; struct ProviderWrapper *
0x18002ba77  mov     [rdi+10h], rdx
0x18002ba7b  mov     r8, r15; unsigned __int64
0x18002ba7e  mov     rcx, rdi; this
0x18002ba81  call    ?ValidateProviderEntry@ResourceHolder@@AEBAKPEBUProviderWrapper@@_K@Z; ResourceHolder::ValidateProviderEntry(ProviderWrapper const *,unsigned __int64)
0x18002ba86  test    eax, eax
0x18002ba88  jnz     short loc_18002BA92
0x18002ba8a  inc     r11d
0x18002ba8d  mov     [rsp+68h+var_38], r11d
0x18002ba92  jmp     short $+2
0x18002ba94  inc     esi
0x18002ba96  add     r10, 14h
0x18002ba9a  mov     [rsp+68h+var_28], r10
0x18002ba9f  jmp     short loc_18002BA3C
0x18002baa1  mov     rax, [rsp+68h+arg_30]
0x18002baa9  mov     [rax], r11d
0x18002baac  cmp     [rsp+68h+arg_20], r11d
0x18002bab4  jnb     short loc_18002BAC1
0x18002bab6  mov     ebx, 7Ah ; 'z'
0x18002babb  mov     [rsp+68h+var_34], ebx
0x18002babf  jmp     short loc_18002BB3F
0x18002bac1  xor     r11d, r11d
0x18002bac4  mov     [rsp+68h+var_38], r11d
0x18002bac9  xor     r10d, r10d
0x18002bacc  mov     rsi, [rsp+68h+arg_28]
0x18002bad4  mov     [rsp+68h+var_2C], r10d
0x18002bad9  mov     [rsp+68h+var_28], r14
0x18002bade  cmp     r10d, [rbx+0Ch]
0x18002bae2  jnb     short loc_18002BB22
0x18002bae4  mov     edx, [r14+10h]
0x18002bae8  add     rdx, [rdi]; struct ProviderWrapper *
0x18002baeb  mov     [rdi+10h], rdx
0x18002baef  mov     r8, r15; unsigned __int64
0x18002baf2  mov     rcx, rdi; this
0x18002baf5  call    ?ValidateProviderEntry@ResourceHolder@@AEBAKPEBUProviderWrapper@@_K@Z; ResourceHolder::ValidateProviderEntry(ProviderWrapper const *,unsigned __int64)
0x18002bafa  test    eax, eax
0x18002bafc  jnz     short loc_18002BB19
0x18002bafe  mov     eax, r11d
0x18002bb01  add     rax, rax
0x18002bb04  movups  xmm0, xmmword ptr [r14]
0x18002bb08  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x18002bb0d  inc     r11d
0x18002bb10  mov     [rsp+68h+var_38], r11d
0x18002bb15  mov     rbx, [rdi+8]
0x18002bb19  inc     r10d
0x18002bb1c  add     r14, 14h
0x18002bb20  jmp     short loc_18002BAD4
0x18002bb22  xor     ebx, ebx
0x18002bb24  jmp     short loc_18002BB3F
0x18002bb26  mov     ebx, 0Dh
0x18002bb2b  mov     [rsp+68h+var_34], ebx
0x18002bb2f  jmp     short loc_18002BB3F
0x18002bb31  mov     ebx, 3EEh
0x18002bb36  mov     [rsp+68h+var_34], ebx
0x18002bb3a  mov     rdi, [rsp+68h+arg_0]
0x18002bb3f  mov     rcx, rdi; this
0x18002bb42  call    ?Close@ResourceHolder@@QEAAXXZ; ResourceHolder::Close(void)
0x18002bb47  mov     eax, ebx
0x18002bb49  lea     r11, [rsp+68h+var_18]
0x18002bb4e  mov     rbx, [r11+28h]
0x18002bb52  mov     rsi, [r11+30h]
0x18002bb56  mov     rsp, r11
0x18002bb59  pop     r15
0x18002bb5b  pop     r14
0x18002bb5d  pop     rdi
0x18002bb5e  retn
0x18004ac83  push    rbp
0x18004ac85  sub     rsp, 30h
0x18004ac89  mov     rbp, rdx
0x18004ac8c  mov     rax, [rcx]
0x18004ac8f  xor     ecx, ecx
0x18004ac91  cmp     dword ptr [rax], 0C0000006h
0x18004ac97  setz    cl
0x18004ac9a  mov     eax, ecx
0x18004ac9c  add     rsp, 30h
0x18004aca0  pop     rbp
0x18004aca1  retn
```
