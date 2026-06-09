# std::vector<Schema::Containers::Definition::RegistryMakeValue,std::allocator<Schema::Containers::Definition::RegistryMakeValue>>::_Tidy(void)

- ea: `0x180021e68`
- end: `0x180021f38`
- name: `?_Tidy@?$vector@URegistryMakeValue@Definition@Containers@Schema@@V?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ`
- size: `208`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180012f40`
- `0x180016110`
- `0x180017470`
- `0x18001c7e4`
- `0x18001efa8`
- `0x180021d98`

## callees

- `0x180002ee4`
- `0x1800051b0`
- `0x18001e6dc`
- `0x180021e68`

## pseudocode

```c
void __fastcall std::vector<Schema::Containers::Definition::RegistryMakeValue>::_Tidy(char **a1)
{
  char *v1; // rbx
  char *v3; // rsi
  char *v4; // rcx
  char *v5; // rax

  v1 = *a1;
  if ( *a1 )
  {
    v3 = a1[1];
    while ( v1 != v3 )
    {
      std::vector<unsigned char>::~vector<unsigned char>(v1 + 120);
      std::wstring::~wstring(v1 + 80);
      std::wstring::~wstring(v1 + 32);
      std::wstring::~wstring(v1);
      v1 += 152;
    }
    v4 = *a1;
    if ( (unsigned __int64)(8 * ((a1[2] - *a1) >> 3)) < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)(v4 - v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x180021e68  mov     [rsp+arg_0], rbx
0x180021e6d  mov     [rsp+arg_8], rsi
0x180021e72  push    rdi
0x180021e73  sub     rsp, 20h
0x180021e77  mov     rbx, [rcx]
0x180021e7a  mov     rdi, rcx
0x180021e7d  test    rbx, rbx
0x180021e80  jz      loc_180021F27
0x180021e86  mov     rsi, [rcx+8]
0x180021e8a  jmp     short loc_180021EB6
0x180021e8c  lea     rcx, [rbx+78h]
0x180021e90  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180021e95  lea     rcx, [rbx+50h]
0x180021e99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021e9e  lea     rcx, [rbx+20h]
0x180021ea2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021ea7  mov     rcx, rbx
0x180021eaa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021eaf  add     rbx, 98h
0x180021eb6  cmp     rbx, rsi
0x180021eb9  jnz     short loc_180021E8C
0x180021ebb  mov     rcx, [rdi]
0x180021ebe  mov     rdx, 86BCA1AF286BCA1Bh
0x180021ec8  mov     rax, [rdi+10h]
0x180021ecc  sub     rax, rcx
0x180021ecf  sar     rax, 3
0x180021ed3  imul    rax, rdx
0x180021ed7  imul    rdx, rax, 98h; unsigned __int64
0x180021ede  cmp     rdx, 1000h
0x180021ee5  jb      short loc_180021F05
0x180021ee7  mov     rax, [rcx-8]
0x180021eeb  sub     rcx, rax
0x180021eee  sub     rcx, 8
0x180021ef2  cmp     rcx, 1Fh
0x180021ef6  ja      short loc_180021EFE
0x180021ef8  add     rdx, 27h ; '''
0x180021efc  jmp     short loc_180021F08
0x180021efe  mov     ecx, 5
0x180021f03  int     29h; Win8: RtlFailFast(ecx)
0x180021f05  mov     rax, rcx
0x180021f08  mov     rcx, rax; void *
0x180021f0b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021f10  mov     qword ptr [rdi], 0
0x180021f17  mov     qword ptr [rdi+8], 0
0x180021f1f  mov     qword ptr [rdi+10h], 0
0x180021f27  mov     rbx, [rsp+28h+arg_0]
0x180021f2c  mov     rsi, [rsp+28h+arg_8]
0x180021f31  add     rsp, 20h
0x180021f35  pop     rdi
0x180021f36  retn
```
