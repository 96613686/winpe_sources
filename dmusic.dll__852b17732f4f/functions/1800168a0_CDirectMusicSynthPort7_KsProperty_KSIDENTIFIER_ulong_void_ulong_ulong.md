# CDirectMusicSynthPort7::KsProperty(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x1800168a0`
- end: `0x180016ad4`
- name: `?KsProperty@CDirectMusicSynthPort7@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `564`
- prototype: `__int64 __usercall@<rax>(CDirectMusicSynthPort7 *__hidden this@<rcx>, struct KSIDENTIFIER *@<rdx>, unsigned int@<r8d>, void *@<r9>, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180011ba0`
- `0x180012160`
- `0x180016500`
- `0x1800168a0`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectMusicSynthPort7::KsProperty(
        CDirectMusicSynthPort7 *this,
        struct KSIDENTIFIER *a2,
        unsigned int a3,
        _DWORD *a4,
        unsigned int a5,
        unsigned int *a6)
{
  __int64 result; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int (__fastcall ***v11)(_QWORD, GUID *, struct IKsControl **); // rcx
  struct IKsControl *v12; // rdx
  __int64 v13; // [rsp+30h] [rbp-28h] BYREF
  struct IKsControl *v14; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v15[3]; // [rsp+40h] [rbp-18h] BYREF

  if ( a3 && !a2 || !a6 )
    return 2147500035LL;
  if ( !*((_QWORD *)this + 2) )
    return 2289570100LL;
  if ( a2->Alignment != *(_QWORD *)&GUID_DMUS_PROP_SetSynthSink.Data1
    || *(&a2->Alignment + 1) != *(_QWORD *)GUID_DMUS_PROP_SetSynthSink.Data4
    || a2->Id )
  {
    return CDirectMusicSynthPort::KsProperty(this, a2, a3, a4, a5, a6);
  }
  if ( (a2->Flags & 0x200) != 0 )
  {
    if ( a5 >= 4 )
    {
      *a4 = 514;
      *a6 = 4;
      return 0;
    }
    return 2147942487LL;
  }
  if ( (*((_BYTE *)&a2->Alignment + 20) & 1) != 0 )
    return 2289570084LL;
  if ( *((_BYTE *)this + 428) )
    return 2289570106LL;
  if ( a5 != 8 )
    return 2147942487LL;
  v8 = *(_QWORD **)a4;
  if ( !*(_QWORD *)a4 || !*v8 || !*(_QWORD *)*v8 )
    return 2147500035LL;
  v15[0] = 0;
  result = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*v8)(v8, &IID_IDirectMusicSynthSink, v15);
  if ( (int)result >= 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 16LL))(*((_QWORD *)this + 48));
    v9 = v15[0];
    *((_QWORD *)this + 48) = v15[0];
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    v10 = *((_QWORD *)this + 2);
    v13 = 0;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v10 + 56LL))(v10, 0, &v13);
    if ( (int)result >= 0 )
    {
      result = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 48) + 32LL))(
                 *((_QWORD *)this + 48),
                 v13);
      if ( (int)result >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        result = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 47) + 112LL))(
                   *((_QWORD *)this + 47),
                   *((_QWORD *)this + 48));
        if ( (int)result >= 0 )
        {
          v11 = (int (__fastcall ***)(_QWORD, GUID *, struct IKsControl **))*((_QWORD *)this + 48);
          v14 = 0;
          if ( (**v11)(v11, &IID_IKsControl, &v14) >= 0 )
          {
            v12 = v14;
          }
          else
          {
            v12 = 0;
            v14 = 0;
          }
          CDirectMusicSynthPort::SetSinkKsControl((CDirectMusicSynthPort7 *)((char *)this - 400), v12);
          CDirectMusicSynthPort7::CacheSinkUsesDSound((CDirectMusicSynthPort7 *)((char *)this - 400));
          return 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800168a0  mov     [rsp+arg_0], rbx
0x1800168a5  push    rdi
0x1800168a6  sub     rsp, 50h
0x1800168aa  mov     rbx, rcx
0x1800168ad  test    r8d, r8d
0x1800168b0  jz      short loc_1800168BB
0x1800168b2  test    rdx, rdx
0x1800168b5  jz      loc_180016AC4
0x1800168bb  mov     rcx, [rsp+58h+arg_28]
0x1800168c3  test    rcx, rcx
0x1800168c6  jz      loc_180016AC4
0x1800168cc  lea     rdi, [rbx-190h]
0x1800168d3  cmp     qword ptr [rdi+1A0h], 0
0x1800168db  jnz     short loc_1800168E7
0x1800168dd  mov     eax, 88781134h
0x1800168e2  jmp     loc_180016AC9
0x1800168e7  mov     rax, [rdx]
0x1800168ea  cmp     rax, qword ptr cs:GUID_DMUS_PROP_SetSynthSink.Data1
0x1800168f1  jnz     loc_180016AAA
0x1800168f7  mov     rax, [rdx+8]
0x1800168fb  cmp     rax, qword ptr cs:GUID_DMUS_PROP_SetSynthSink.Data4
0x180016902  jnz     loc_180016AAA
0x180016908  cmp     dword ptr [rdx+10h], 0
0x18001690c  jnz     loc_180016AAA
0x180016912  test    dword ptr [rdx+14h], 200h
0x180016919  jz      short loc_180016939
0x18001691b  cmp     [rsp+58h+arg_20], 4
0x180016923  jb      short loc_180016966
0x180016925  mov     dword ptr [r9], 202h
0x18001692c  mov     dword ptr [rcx], 4
0x180016932  xor     eax, eax
0x180016934  jmp     loc_180016AC9
0x180016939  test    byte ptr [rdx+14h], 1
0x18001693d  jz      short loc_180016949
0x18001693f  mov     eax, 88781124h
0x180016944  jmp     loc_180016AC9
0x180016949  cmp     byte ptr [rbx+1ACh], 0
0x180016950  jz      short loc_18001695C
0x180016952  mov     eax, 8878113Ah
0x180016957  jmp     loc_180016AC9
0x18001695c  cmp     [rsp+58h+arg_20], 8
0x180016964  jz      short loc_180016970
0x180016966  mov     eax, 80070057h
0x18001696b  jmp     loc_180016AC9
0x180016970  mov     rcx, [r9]
0x180016973  test    rcx, rcx
0x180016976  jz      loc_180016AC4
0x18001697c  mov     rax, [rcx]
0x18001697f  test    rax, rax
0x180016982  jz      loc_180016AC4
0x180016988  cmp     qword ptr [rax], 0
0x18001698c  jz      loc_180016AC4
0x180016992  mov     [rsp+58h+var_18], 0
0x18001699b  lea     r8, [rsp+58h+var_18]
0x1800169a0  mov     rax, [rcx]
0x1800169a3  lea     rdx, IID_IDirectMusicSynthSink
0x1800169aa  mov     rax, [rax]
0x1800169ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169b2  test    eax, eax
0x1800169b4  js      loc_180016AC9
0x1800169ba  mov     rcx, [rbx+180h]
0x1800169c1  mov     rax, [rcx]
0x1800169c4  mov     rax, [rax+10h]
0x1800169c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169cd  mov     rcx, [rsp+58h+var_18]
0x1800169d2  mov     [rbx+180h], rcx
0x1800169d9  mov     rax, [rcx]
0x1800169dc  mov     rax, [rax+8]
0x1800169e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169e5  mov     rcx, [rbx+10h]
0x1800169e9  lea     r8, [rsp+58h+var_28]
0x1800169ee  mov     [rsp+58h+var_28], 0
0x1800169f7  xor     edx, edx
0x1800169f9  mov     rax, [rcx]
0x1800169fc  mov     rax, [rax+38h]
0x180016a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a05  test    eax, eax
0x180016a07  js      loc_180016AC9
0x180016a0d  mov     rcx, [rbx+180h]
0x180016a14  mov     rdx, [rsp+58h+var_28]
0x180016a19  mov     rax, [rcx]
0x180016a1c  mov     rax, [rax+20h]
0x180016a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a25  test    eax, eax
0x180016a27  js      loc_180016AC9
0x180016a2d  mov     rcx, [rsp+58h+var_28]
0x180016a32  mov     rax, [rcx]
0x180016a35  mov     rax, [rax+10h]
0x180016a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a3e  mov     rcx, [rbx+178h]
0x180016a45  mov     rdx, [rbx+180h]
0x180016a4c  mov     rax, [rcx]
0x180016a4f  mov     rax, [rax+70h]
0x180016a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a58  test    eax, eax
0x180016a5a  js      short loc_180016AC9
0x180016a5c  mov     rcx, [rbx+180h]
0x180016a63  lea     r8, [rsp+58h+var_20]
0x180016a68  mov     [rsp+58h+var_20], 0
0x180016a71  lea     rdx, IID_IKsControl
0x180016a78  mov     rax, [rcx]
0x180016a7b  mov     rax, [rax]
0x180016a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a83  test    eax, eax
0x180016a85  jns     short loc_180016A90
0x180016a87  xor     edx, edx
0x180016a89  mov     [rsp+58h+var_20], rdx
0x180016a8e  jmp     short loc_180016A95
0x180016a90  mov     rdx, [rsp+58h+var_20]; struct IKsControl *
0x180016a95  mov     rcx, rdi; this
0x180016a98  call    ?SetSinkKsControl@CDirectMusicSynthPort@@IEAAXPEAUIKsControl@@@Z; CDirectMusicSynthPort::SetSinkKsControl(IKsControl *)
0x180016a9d  mov     rcx, rdi; this
0x180016aa0  call    ?CacheSinkUsesDSound@CDirectMusicSynthPort7@@AEAAXXZ; CDirectMusicSynthPort7::CacheSinkUsesDSound(void)
0x180016aa5  jmp     loc_180016932
0x180016aaa  mov     eax, [rsp+58h+arg_20]
0x180016ab1  mov     [rsp+58h+var_30], rcx; unsigned int *
0x180016ab6  mov     rcx, rbx; this
0x180016ab9  mov     [rsp+58h+var_38], eax; unsigned int
0x180016abd  call    ?KsProperty@CDirectMusicSynthPort@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z; CDirectMusicSynthPort::KsProperty(KSIDENTIFIER *,ulong,void *,ulong,ulong *)
0x180016ac2  jmp     short loc_180016AC9
0x180016ac4  mov     eax, 80004003h
0x180016ac9  mov     rbx, [rsp+58h+arg_0]
0x180016ace  add     rsp, 50h
0x180016ad2  pop     rdi
0x180016ad3  retn
```
