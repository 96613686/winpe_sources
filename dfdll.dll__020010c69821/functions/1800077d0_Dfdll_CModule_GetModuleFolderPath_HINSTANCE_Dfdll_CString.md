# Dfdll::CModule::GetModuleFolderPath(HINSTANCE__ *,Dfdll::CString &)

- ea: `0x1800077d0`
- end: `0x180007917`
- name: `?GetModuleFolderPath@CModule@Dfdll@@SAJPEAUHINSTANCE__@@AEAVCString@2@@Z`
- size: `327`
- prototype: `static int(HINSTANCE, struct Dfdll::CString *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180007a7c`
- `0x18000d59c`

## callees

- `0x180002238`
- `0x180002ff8`
- `0x1800077d0`
- `0x180012b30`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CModule::GetModuleFolderPath(HINSTANCE a1, struct Dfdll::CString *a2)
{
  const struct std::nothrow_t *v3; // rdx
  int ModuleFileNameW; // ebx
  unsigned __int16 *v5; // rsi
  unsigned int v6; // edi
  __int64 v7; // rax
  bool v8; // zf
  const struct std::nothrow_t *v9; // rdx
  void **v11; // [rsp+20h] [rbp-30h] BYREF
  void **v12; // [rsp+28h] [rbp-28h]
  unsigned __int16 *v13; // [rsp+30h] [rbp-20h]
  int v14; // [rsp+38h] [rbp-18h]
  int v15; // [rsp+40h] [rbp-10h]

  v11 = &Dfdll::CString::`vftable';
  v13 = 0;
  v14 = 0;
  v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v15 = 0;
  ModuleFileNameW = Dfdll::CSystem::GetModuleFileNameW(a1, (struct Dfdll::CString *)&v11);
  if ( ModuleFileNameW >= 0 )
  {
    v5 = v13;
    if ( v13 )
    {
      v6 = v15 - 1;
      v7 = v15 - 1;
      v8 = v15 == 1;
      if ( v15 - 1 > 0 )
      {
        do
        {
          if ( v13[v7] == 92 )
            break;
          --v6;
          --v7;
        }
        while ( v7 > 0 );
        v8 = v6 == 0;
      }
      if ( v8 )
      {
        ModuleFileNameW = -2147024883;
        v11 = &Dfdll::CString::`vftable';
        v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
        operator delete(v13, v3);
      }
      else if ( *((_DWORD *)a2 + 8)
             && (ModuleFileNameW = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)a2 + 1) + 40LL))(
                                     (char *)a2 + 8,
                                     0),
                 ModuleFileNameW < 0)
             || (*((_DWORD *)a2 + 8) = 0,
                 ModuleFileNameW = Dfdll::CString::Append(a2, (struct std::nothrow_t *)v5, v6),
                 ModuleFileNameW < 0) )
      {
        v11 = &Dfdll::CString::`vftable';
        v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
        if ( v13 )
          operator delete(v13, v9);
      }
      else
      {
        ModuleFileNameW = 0;
        v11 = &Dfdll::CString::`vftable';
        v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
        if ( v13 )
          operator delete(v13, v9);
      }
    }
    else
    {
      return (unsigned int)-2147024883;
    }
  }
  else
  {
    v11 = &Dfdll::CString::`vftable';
    v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v13 )
      operator delete(v13, v3);
  }
  return (unsigned int)ModuleFileNameW;
}

```

## disassembly

```asm
0x1800077d0  mov     rax, rsp
0x1800077d3  mov     [rax+8], rbx
0x1800077d7  mov     [rax+10h], rsi
0x1800077db  mov     [rax+18h], rdi
0x1800077df  mov     [rax+20h], r12
0x1800077e3  push    rbp
0x1800077e4  push    r13
0x1800077e6  push    r14
0x1800077e8  mov     rbp, rsp
0x1800077eb  sub     rsp, 50h
0x1800077ef  mov     r14, rdx
0x1800077f2  lea     r12, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x1800077f9  mov     [rbp+var_30], r12
0x1800077fd  and     [rbp+var_20], 0
0x180007802  and     [rbp+var_18], 0
0x180007806  lea     r13, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000780d  mov     [rbp+var_28], r13
0x180007811  and     [rbp+var_10], 0
0x180007815  lea     rdx, [rbp+var_30]; this
0x180007819  call    ?GetModuleFileNameW@CSystem@Dfdll@@SAJPEAUHINSTANCE__@@AEAVCString@2@@Z; Dfdll::CSystem::GetModuleFileNameW(HINSTANCE__ *,Dfdll::CString &)
0x18000781e  mov     ebx, eax
0x180007820  test    eax, eax
0x180007822  jns     short loc_180007840
0x180007824  mov     [rbp+var_30], r12
0x180007828  mov     [rbp+var_28], r13
0x18000782c  mov     rcx, [rbp+var_20]; void *
0x180007830  test    rcx, rcx
0x180007833  jz      short loc_18000783B
0x180007835  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000783a  nop
0x18000783b  jmp     loc_1800078F7
0x180007840  mov     rsi, [rbp+var_20]
0x180007844  test    rsi, rsi
0x180007847  jnz     short loc_180007853
0x180007849  mov     ebx, 8007000Dh
0x18000784e  jmp     loc_1800078F7
0x180007853  mov     edi, [rbp+var_10]
0x180007856  dec     edi
0x180007858  movsxd  rax, edi
0x18000785b  test    edi, edi
0x18000785d  jle     short loc_180007872
0x18000785f  cmp     word ptr [rsi+rax*2], 5Ch ; '\'
0x180007864  jz      short loc_180007870
0x180007866  dec     edi
0x180007868  dec     rax
0x18000786b  test    rax, rax
0x18000786e  jg      short loc_18000785F
0x180007870  test    edi, edi
0x180007872  jnz     short loc_18000788C
0x180007874  mov     ebx, 8007000Dh
0x180007879  mov     [rbp+var_30], r12
0x18000787d  mov     [rbp+var_28], r13
0x180007881  mov     rcx, rsi; void *
0x180007884  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007889  nop
0x18000788a  jmp     short loc_1800078F7
0x18000788c  cmp     dword ptr [r14+20h], 0
0x180007891  jbe     short loc_1800078AC
0x180007893  lea     rcx, [r14+8]
0x180007897  mov     rax, [rcx]
0x18000789a  xor     edx, edx
0x18000789c  mov     rax, [rax+28h]
0x1800078a0  call    cs:__guard_dispatch_icall_fptr
0x1800078a6  mov     ebx, eax
0x1800078a8  test    eax, eax
0x1800078aa  js      short loc_1800078E0
0x1800078ac  and     dword ptr [r14+20h], 0
0x1800078b1  mov     r8d, edi; unsigned int
0x1800078b4  mov     rdx, rsi; unsigned __int16 *
0x1800078b7  mov     rcx, r14; this
0x1800078ba  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x1800078bf  mov     ebx, eax
0x1800078c1  test    eax, eax
0x1800078c3  js      short loc_1800078E0
0x1800078c5  xor     ebx, ebx
0x1800078c7  mov     [rbp+var_30], r12
0x1800078cb  mov     [rbp+var_28], r13
0x1800078cf  mov     rcx, [rbp+var_20]; void *
0x1800078d3  test    rcx, rcx
0x1800078d6  jz      short loc_1800078DE
0x1800078d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800078dd  nop
0x1800078de  jmp     short loc_1800078F7
0x1800078e0  mov     [rbp+var_30], r12
0x1800078e4  mov     [rbp+var_28], r13
0x1800078e8  mov     rcx, [rbp+var_20]; void *
0x1800078ec  test    rcx, rcx
0x1800078ef  jz      short loc_1800078F7
0x1800078f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800078f6  nop
0x1800078f7  mov     eax, ebx
0x1800078f9  lea     r11, [rsp+50h+var_s0]
0x1800078fe  mov     rbx, [r11+20h]
0x180007902  mov     rsi, [r11+28h]
0x180007906  mov     rdi, [r11+30h]
0x18000790a  mov     r12, [r11+38h]
0x18000790e  mov     rsp, r11
0x180007911  pop     r14
0x180007913  pop     r13
0x180007915  pop     rbp
0x180007916  retn
```
