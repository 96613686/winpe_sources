# NOutermost::CDevice::CreateLayeredChild(uint,void const *,unsigned __int64,ID3D12LayeredUseCounted *,_GUID const &,void * *)

- ea: `0x1800014c0`
- end: `0x180001954`
- name: `?CreateLayeredChild@CDevice@NOutermost@@UEAAJIPEBX_KPEAUID3D12LayeredUseCounted@@AEBU_GUID@@PEAPEAX@Z`
- size: `1172`
- prototype: `__int64 __fastcall(NOutermost::CDevice *this, int, const void *, size_t, struct ID3D12LayeredUseCounted *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800014c0`
- `0x18000195c`
- `0x18000b410`
- `0x18000b81c`
- `0x18000be84`
- `0x18000c335`
- `0x180013a50`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall NOutermost::CDevice::CreateLayeredChild(
        NOutermost::CDevice *this,
        int a2,
        const void *a3,
        size_t a4,
        struct ID3D12LayeredUseCounted *a5,
        struct _GUID *a6,
        void **a7)
{
  unsigned __int64 v9; // r14
  volatile signed __int64 *v10; // rdi
  __int64 v11; // rax
  void *v12; // rsp
  _QWORD *v13; // r14
  int v14; // ecx
  int v15; // ecx
  _QWORD *i; // rbx
  __int64 (__fastcall *v17)(volatile signed __int64 *, struct _GUID *, void **, _QWORD); // rax
  _DWORD *v18; // rdx
  int v19; // r12d
  int v20; // eax
  int v21; // ecx
  __int64 result; // rax
  char *v23; // rbx
  volatile signed __int64 *v24; // rbx
  __int64 v25; // rax
  void *v26; // rsp
  volatile signed __int64 *v27; // [rsp+40h] [rbp+0h] BYREF
  NOutermost::CDevice *v28; // [rsp+48h] [rbp+8h]
  volatile signed __int64 *v29; // [rsp+50h] [rbp+10h] BYREF
  volatile signed __int64 **v30; // [rsp+58h] [rbp+18h]
  size_t v31; // [rsp+60h] [rbp+20h]
  volatile signed __int64 *v32; // [rsp+68h] [rbp+28h]
  volatile signed __int64 *v33; // [rsp+70h] [rbp+30h]
  volatile signed __int64 *v34; // [rsp+78h] [rbp+38h]
  _com_error *v35; // [rsp+80h] [rbp+40h] BYREF
  void **pExceptionObject; // [rsp+88h] [rbp+48h] BYREF
  int v37; // [rsp+90h] [rbp+50h]
  __int128 v38; // [rsp+98h] [rbp+58h]
  void **v39; // [rsp+A8h] [rbp+68h] BYREF
  int v40; // [rsp+B0h] [rbp+70h]
  __int128 v41; // [rsp+B8h] [rbp+78h]
  void **v42; // [rsp+C8h] [rbp+88h] BYREF
  int v43; // [rsp+D0h] [rbp+90h]
  __int128 v44; // [rsp+D8h] [rbp+98h]
  void **v45; // [rsp+E8h] [rbp+A8h] BYREF
  int v46; // [rsp+F0h] [rbp+B0h]
  __int128 v47; // [rsp+F8h] [rbp+B8h]
  void **v48; // [rsp+108h] [rbp+C8h] BYREF
  int v49; // [rsp+110h] [rbp+D0h]
  __int128 v50; // [rsp+118h] [rbp+D8h]

  try
  {
    LODWORD(v27) = a2;
    v28 = this;
    if ( !a7 )
    {
      pExceptionObject = &_com_error::`vftable';
      v37 = -2147418113;
      v38 = 0;
      throw (_com_error *)&pExceptionObject;
    }
    *a7 = 0;
    if ( a4 < 0x10 )
    {
      v39 = &_com_error::`vftable';
      v40 = -2147418113;
      v41 = 0;
      throw (_com_error *)&v39;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 64LL))(*((_QWORD *)this + 12)) + 32;
    if ( a5 )
    {
      if ( v9 < 0x20 )
        v9 = -1;
      v24 = (volatile signed __int64 *)operator new[](v9);
      v33 = v24;
      v25 = a4 + 15;
      if ( a4 + 15 < a4 )
        v25 = 0xFFFFFFFFFFFFFF0LL;
      v26 = alloca(v25 & 0xFFFFFFFFFFFFFFF0uLL);
      memcpy_0(&v27, a3, a4);
      v27 = v24 + 4;
      v28 = (NOutermost::CDevice *)(v9 - 32);
      v29 = (volatile signed __int64 *)(unsigned int)((_DWORD)v24 + 32);
      v30 = &v27;
      v31 = a4;
      CDelegatingUseCountedObject<NOutermost::CDeviceChild>::CreateInstance(
        (struct NOutermost::CDeviceChild::TConstructorArgs *)&v29,
        a6,
        a7);
      result = 0;
    }
    else
    {
      if ( v9 < 0x20 )
        v9 = -1;
      v10 = (volatile signed __int64 *)operator new[](v9);
      v34 = v10;
      v11 = a4 + 15;
      if ( a4 + 15 < a4 )
        v11 = 0xFFFFFFFFFFFFFF0LL;
      v12 = alloca(v11 & 0xFFFFFFFFFFFFFFF0uLL);
      memcpy_0(&v27, a3, a4);
      v27 = v10 + 4;
      v28 = (NOutermost::CDevice *)(v9 - 32);
      HIDWORD(v29) = 0;
      v32 = 0;
      if ( !v10 )
      {
        v10 = (volatile signed __int64 *)operator new[](0x20u);
        v32 = v10;
      }
      v33 = v10;
      *((_QWORD *)v10 + 2) = v28;
      *((_QWORD *)v10 + 1) = 0;
      v13 = v10 + 3;
      *((_QWORD *)v10 + 3) = 0;
      *v10 = (volatile signed __int64)&CUseCountedObject<NOutermost::CDeviceChild>::`vftable';
      v28 = (NOutermost::CDevice *)v10;
      v29 = v10;
      LOBYTE(v30) = 0;
      _InterlockedAdd64(v10 + 1, 0x100000000uLL);
      v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, volatile signed __int64 **, size_t, volatile signed __int64 *, GUID *, volatile signed __int64 *))(**(_QWORD **)(*((_QWORD *)v10 + 2) + 96LL) + 72LL))(
              *(_QWORD *)(*((_QWORD *)v10 + 2) + 96LL),
              (unsigned int)v27,
              &v27,
              a4,
              v10,
              &GUID_8d7c0ced_36c4_45a8_88f7_69e74d0ebf1a,
              v10 + 3);
      if ( v14 < 0 )
      {
        v42 = &_com_error::`vftable';
        v43 = v14;
        v44 = 0;
        throw (_com_error *)&v42;
      }
      v15 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*v10 + 64))(v10);
      if ( v15 < 0 )
      {
        v45 = &_com_error::`vftable';
        v46 = v15;
        v47 = 0;
        throw (_com_error *)&v45;
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 96LL))(*v13);
      *a7 = 0;
      if ( !*(_QWORD *)&a6->Data1 && *(_DWORD *)a6->Data4 == 192 && *(_DWORD *)&a6->Data4[4] == 1174405120 )
      {
        (*(void (__fastcall **)(volatile signed __int64 *))(*v10 + 8))(v10);
        *a7 = (void *)v10;
        v21 = 0;
        goto LABEL_26;
      }
      for ( i = &`NOutermost::CDeviceChild::_GetEntries'::`2'::_entries; ; i += 3 )
      {
        v17 = (__int64 (__fastcall *)(volatile signed __int64 *, struct _GUID *, void **, _QWORD))i[2];
        if ( !v17 )
        {
          v21 = -2147467262;
          goto LABEL_26;
        }
        v18 = (_DWORD *)*i;
        if ( *i )
        {
          if ( *v18 != a6->Data1
            || v18[1] != *(_DWORD *)&a6->Data2
            || v18[2] != *(_DWORD *)a6->Data4
            || v18[3] != *(_DWORD *)&a6->Data4[4] )
          {
            continue;
          }
          v19 = 0;
        }
        else
        {
          v19 = 1;
        }
        if ( v17 == (__int64 (__fastcall *)(volatile signed __int64 *, struct _GUID *, void **, _QWORD))1 )
          break;
        v20 = v17(v10, a6, a7, i[1]);
        v21 = v20;
        if ( !v20 || !v19 && v20 < 0 )
          goto LABEL_26;
      }
      v23 = (char *)v10 + i[1];
      (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 8LL))(v23);
      *a7 = v23;
      v21 = 0;
LABEL_26:
      if ( v21 < 0 )
      {
        v48 = &_com_error::`vftable';
        v49 = v21;
        v50 = 0;
        throw (_com_error *)&v48;
      }
      if ( (unsigned __int64)(_InterlockedExchangeAdd64(v10 + 1, 0xFFFFFFFF00000000uLL) - 0x100000000LL) >> 32 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 48LL))(*v13);
      result = 0;
    }
  }
  catch ( std::exception )
  {
    return 2147942414LL;
  }
  catch ( _com_error *v35 )
  {
    return *((unsigned int *)v35 + 2);
  }
  LODWORD(v27) = a2;
}

```

## disassembly

```asm
0x1800014c0  push    rbp
0x1800014c2  push    rbx
0x1800014c3  push    rsi
0x1800014c4  push    rdi
0x1800014c5  push    r12
0x1800014c7  push    r13
0x1800014c9  push    r14
0x1800014cb  push    r15
0x1800014cd  sub     rsp, 138h
0x1800014d4  lea     rbp, [rsp+40h]
0x1800014d9  mov     rax, cs:__security_cookie
0x1800014e0  xor     rax, rbp
0x1800014e3  mov     [rbp+130h+var_48], rax
0x1800014ea  mov     rsi, r9
0x1800014ed  mov     r13, r8
0x1800014f0  mov     dword ptr [rbp+130h+var_130], edx
0x1800014f3  mov     [rbp+130h+var_128], rcx
0x1800014f7  mov     r15, [rbp+130h+arg_30]
0x1800014fe  test    r15, r15
0x180001501  jnz     short loc_18000152D
0x180001503  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000150a  mov     [rbp+130h+pExceptionObject], rax
0x18000150e  mov     [rbp+130h+var_E0], 8000FFFFh
0x180001515  xorps   xmm0, xmm0
0x180001518  movdqu  [rbp+130h+var_D8], xmm0
0x18000151d  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180001524  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x180001528  call    _CxxThrowException_0
0x18000152d  mov     qword ptr [r15], 0
0x180001534  cmp     rsi, 10h
0x180001538  jnb     short loc_180001564
0x18000153a  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180001541  mov     [rbp+130h+var_C8], rax
0x180001545  mov     [rbp+130h+var_C0], 8000FFFFh
0x18000154c  xorps   xmm0, xmm0
0x18000154f  movdqu  [rbp+130h+var_B8], xmm0
0x180001554  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18000155b  lea     rcx, [rbp+130h+var_C8]; pExceptionObject
0x18000155f  call    _CxxThrowException_0
0x180001564  mov     rcx, [rcx+60h]
0x180001568  mov     rax, [rcx]
0x18000156b  mov     rax, [rax+40h]
0x18000156f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001574  lea     r14, [rax+20h]
0x180001578  mov     r12, [rbp+130h+arg_20]
0x18000157f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001586  test    r12, r12
0x180001589  jnz     loc_18000189E
0x18000158f  cmp     r14, 20h ; ' '
0x180001593  cmovb   r14, rax
0x180001597  mov     rcx, r14; unsigned __int64
0x18000159a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000159f  mov     rdi, rax
0x1800015a2  mov     [rbp+130h+var_F8], rax
0x1800015a6  lea     rax, [rsi+0Fh]
0x1800015aa  cmp     rax, rsi
0x1800015ad  ja      short loc_1800015B9
0x1800015af  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800015b9  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800015bd  call    _alloca_probe
0x1800015c2  sub     rsp, rax
0x1800015c5  lea     rbx, [rsp+170h+var_130]
0x1800015ca  mov     r8, rsi; Size
0x1800015cd  mov     rdx, r13; Src
0x1800015d0  mov     rcx, rbx; void *
0x1800015d3  call    memcpy_0
0x1800015d8  lea     rax, [rdi+20h]
0x1800015dc  mov     [rbx], rax
0x1800015df  lea     rax, [r14-20h]
0x1800015e3  mov     [rbx+8], rax
0x1800015e7  xor     eax, eax
0x1800015e9  mov     [rbp+130h+var_11C], eax
0x1800015ec  xor     r13d, r13d
0x1800015ef  mov     [rbp+130h+var_108], r13
0x1800015f3  test    rdi, rdi
0x1800015f6  jnz     short loc_180001609
0x1800015f8  mov     ecx, 20h ; ' '; unsigned __int64
0x1800015fd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180001602  mov     rdi, rax
0x180001605  mov     [rbp+130h+var_108], rax
0x180001609  mov     [rbp+130h+var_100], rdi
0x18000160d  mov     rdx, [rbp+130h+var_128]
0x180001611  mov     [rdi+10h], rdx
0x180001615  mov     [rdi+8], r13
0x180001619  lea     r14, [rdi+18h]
0x18000161d  mov     [r14], r13
0x180001620  lea     rax, ??_7?$CUseCountedObject@VCDeviceChild@NOutermost@@@@6B@; const CUseCountedObject<NOutermost::CDeviceChild>::`vftable'
0x180001627  mov     [rdi], rax
0x18000162a  mov     [rbp+130h+var_128], rdi
0x18000162e  mov     [rbp+10h], rdi
0x180001632  mov     byte ptr [rbp+130h+var_118], 0
0x180001636  mov     r12, 100000000h
0x180001640  lock add [rdi+8], r12
0x180001645  mov     rax, [rdi+10h]
0x180001649  mov     rcx, [rax+60h]
0x18000164d  mov     rax, [rcx]
0x180001650  mov     [rsp+170h+var_140], r14
0x180001655  lea     rdx, _GUID_8d7c0ced_36c4_45a8_88f7_69e74d0ebf1a
0x18000165c  mov     [rsp+170h+var_148], rdx
0x180001661  mov     [rsp+170h+var_150], rdi
0x180001666  mov     r9, rsi
0x180001669  mov     r8, rbx
0x18000166c  mov     edx, dword ptr [rbp+130h+var_130]
0x18000166f  mov     rax, [rax+48h]
0x180001673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001678  mov     ecx, eax
0x18000167a  test    eax, eax
0x18000167c  jns     short loc_1800016B0
0x18000167e  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180001685  mov     [rbp+130h+var_A8], rax
0x18000168c  mov     [rbp+130h+var_A0], ecx
0x180001692  xorps   xmm0, xmm0
0x180001695  movdqu  [rbp+130h+var_98], xmm0
0x18000169d  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x1800016a4  lea     rcx, [rbp+130h+var_A8]; pExceptionObject
0x1800016ab  call    _CxxThrowException_0
0x1800016b0  mov     rax, [rdi]
0x1800016b3  mov     rcx, rdi
0x1800016b6  mov     rax, [rax+40h]
0x1800016ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016bf  mov     ecx, eax
0x1800016c1  test    eax, eax
0x1800016c3  jns     short loc_1800016F8
0x1800016c5  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800016cc  mov     [rbp+130h+var_88], rax
0x1800016d3  mov     [rbp+130h+var_80], ecx
0x1800016d9  xorps   xmm0, xmm0
0x1800016dc  movdqu  [rbp+130h+var_78], xmm0
0x1800016e4  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x1800016eb  lea     rcx, [rbp+130h+var_88]; pExceptionObject
0x1800016f2  call    _CxxThrowException_0
0x1800016f8  mov     rcx, [r14]
0x1800016fb  mov     rax, [rcx]
0x1800016fe  mov     rax, [rax+60h]
0x180001702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001707  nop
0x180001708  mov     [r15], r13
0x18000170b  mov     rsi, [rbp+130h+arg_28]
0x180001712  cmp     dword ptr [rsi], 0
0x180001715  jz      loc_180001813
0x18000171b  lea     rbx, ?_entries@?1??_GetEntries@CDeviceChild@NOutermost@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU45@B; ATL::_ATL_INTMAP_ENTRY const near * const `NOutermost::CDeviceChild::_GetEntries(void)'::`2'::_entries
0x180001722  mov     rax, [rbx+10h]
0x180001726  test    rax, rax
0x180001729  jz      loc_180001809
0x18000172f  mov     rdx, [rbx]
0x180001732  test    rdx, rdx
0x180001735  jz      short loc_180001747
0x180001737  mov     ecx, [rsi]
0x180001739  cmp     [rdx], ecx
0x18000173b  jz      loc_180001851
0x180001741  add     rbx, 18h
0x180001745  jmp     short loc_180001722
0x180001747  mov     r12d, 1
0x18000174d  cmp     rax, 1
0x180001751  jz      loc_18000187D
0x180001757  mov     r9, [rbx+8]
0x18000175b  mov     r8, r15
0x18000175e  mov     rdx, rsi
0x180001761  mov     rcx, rdi
0x180001764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001769  mov     ecx, eax
0x18000176b  test    eax, eax
0x18000176d  jnz     short loc_1800017AF
0x18000176f  mov     r12, 100000000h
0x180001779  test    ecx, ecx
0x18000177b  jns     short loc_1800017B9
0x18000177d  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180001784  mov     [rbp+130h+var_68], rax
0x18000178b  mov     [rbp+130h+var_60], ecx
0x180001791  xorps   xmm0, xmm0
0x180001794  movdqu  [rbp+130h+var_58], xmm0
0x18000179c  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x1800017a3  lea     rcx, [rbp+130h+var_68]; pExceptionObject
0x1800017aa  call    _CxxThrowException_0
0x1800017af  test    r12d, r12d
0x1800017b2  jnz     short loc_180001741
0x1800017b4  jmp     loc_180001935
0x1800017b9  mov     rax, 0FFFFFFFF00000000h
0x1800017c3  lock xadd [rdi+8], rax
0x1800017c9  sub     rax, r12
0x1800017cc  shr     rax, 20h
0x1800017d0  test    eax, eax
0x1800017d2  jz      short loc_1800017E4
0x1800017d4  mov     rcx, [r14]
0x1800017d7  mov     rax, [rcx]
0x1800017da  mov     rax, [rax+30h]
0x1800017de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017e3  nop
0x1800017e4  xor     eax, eax
0x1800017e6  mov     rcx, [rbp+130h+var_48]
0x1800017ed  xor     rcx, rbp; StackCookie
0x1800017f0  call    __security_check_cookie
0x1800017f5  lea     rsp, [rbp+0F8h]
0x1800017fc  pop     r15
0x1800017fe  pop     r14
0x180001800  pop     r13
0x180001802  pop     r12
0x180001804  pop     rdi
0x180001805  pop     rsi
0x180001806  pop     rbx
0x180001807  pop     rbp
0x180001808  retn
0x180001809  mov     ecx, 80004002h
0x18000180e  jmp     loc_18000176F
0x180001813  cmp     dword ptr [rsi+4], 0
0x180001817  jnz     loc_18000171B
0x18000181d  cmp     dword ptr [rsi+8], 0C0h
0x180001824  jnz     loc_18000171B
0x18000182a  cmp     dword ptr [rsi+0Ch], 46000000h
0x180001831  jnz     loc_18000171B
0x180001837  mov     rax, [rdi]
0x18000183a  mov     rcx, rdi
0x18000183d  mov     rax, [rax+8]
0x180001841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001846  mov     [r15], rdi
0x180001849  mov     ecx, r13d
0x18000184c  jmp     loc_180001779
0x180001851  mov     ecx, [rsi+4]
0x180001854  cmp     [rdx+4], ecx
0x180001857  jnz     loc_180001741
0x18000185d  mov     ecx, [rsi+8]
0x180001860  cmp     [rdx+8], ecx
0x180001863  jnz     loc_180001741
0x180001869  mov     ecx, [rsi+0Ch]
0x18000186c  cmp     [rdx+0Ch], ecx
0x18000186f  jnz     loc_180001741
0x180001875  mov     r12d, r13d
0x180001878  jmp     loc_18000174D
0x18000187d  mov     rbx, [rbx+8]
0x180001881  add     rbx, rdi
0x180001884  mov     rax, [rbx]
0x180001887  mov     rcx, rbx
0x18000188a  mov     rax, [rax+8]
0x18000188e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001893  mov     [r15], rbx
0x180001896  mov     ecx, r13d
0x180001899  jmp     loc_18000176F
0x18000189e  cmp     r14, 20h ; ' '
0x1800018a2  cmovb   r14, rax
0x1800018a6  mov     rcx, r14; unsigned __int64
0x1800018a9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800018ae  mov     rbx, rax
0x1800018b1  mov     [rbp+130h+var_100], rax
0x1800018b5  lea     rax, [rsi+0Fh]
0x1800018b9  cmp     rax, rsi
0x1800018bc  ja      short loc_1800018C8
0x1800018be  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800018c8  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800018cc  call    _alloca_probe
0x1800018d1  sub     rsp, rax
0x1800018d4  lea     rdi, [rsp+170h+var_130]
0x1800018d9  mov     r8, rsi; Size
0x1800018dc  mov     rdx, r13; Src
0x1800018df  mov     rcx, rdi; void *
0x1800018e2  call    memcpy_0
0x1800018e7  lea     rax, [rbx+20h]
0x1800018eb  mov     [rdi], rax
0x1800018ee  lea     rax, [r14-20h]
0x1800018f2  mov     [rdi+8], rax
0x1800018f6  mov     edx, dword ptr [rbp+130h+var_130]
0x1800018f9  mov     [rbp+130h+var_120], edx
0x1800018fc  xor     eax, eax
0x1800018fe  mov     [rbp+130h+var_11C], eax
0x180001901  mov     [rbp+130h+var_118], rdi
0x180001905  mov     [rbp+130h+var_110], rsi
0x180001909  mov     [rsp+170h+var_148], r15; void **
0x18000190e  mov     rax, [rbp+130h+arg_28]
0x180001915  mov     [rsp+170h+var_150], rax; struct _GUID *
0x18000191a  mov     r9, r12
0x18000191d  mov     r8, rbx
0x180001920  mov     rdx, [rbp+130h+var_128]
0x180001924  lea     rcx, [rbp+130h+var_120]; struct NOutermost::CDeviceChild::TConstructorArgs *
0x180001928  call    ?CreateInstance@?$CDelegatingUseCountedObject@VCDeviceChild@NOutermost@@@@SAXAEBUTConstructorArgs@CDeviceChild@NOutermost@@PEAVCDevice@4@PEAX2AEBU_GUID@@PEAPEAX@Z; CDelegatingUseCountedObject<NOutermost::CDeviceChild>::CreateInstance(NOutermost::CDeviceChild::TConstructorArgs const &,NOutermost::CDevice *,void *,void *,_GUID const &,void * *)
0x18000192d  nop
0x18000192e  xor     eax, eax
0x180001930  jmp     loc_1800017E6
0x180001935  test    eax, eax
0x180001937  jns     loc_180001741
0x18000193d  jmp     loc_18000176F
0x180001942  mov     eax, 8007000Eh
0x180001947  jmp     loc_1800017E6
0x18000194c  mov     eax, dword ptr [rbp+130h+var_130]
0x18000194f  jmp     loc_1800017E6
```
