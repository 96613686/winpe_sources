# CWMWriter::NonDelegatingQueryInterface(_GUID const &,void * *)

- ea: `0x1800105e0`
- end: `0x1800107a5`
- name: `?NonDelegatingQueryInterface@CWMWriter@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `453`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x180005450`
- `0x1800105e0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriter::NonDelegatingQueryInterface(CWMWriter *this, const struct _GUID *a2, void **a3)
{
  unsigned int v3; // ebx
  void *v4; // rcx
  void (*v5)(void); // rax
  unsigned __int64 v7; // rax
  void *v8; // rcx

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMediaSeeking.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IMediaSeeking.Data4 )
  {
    v3 = 0;
    v4 = (void *)(((unsigned __int64)this + 120) & -(__int64)(this != 0));
    if ( !a3 )
      return (unsigned int)-2147467261;
    *a3 = v4;
    v5 = *(void (**)(void))(*(_QWORD *)v4 + 8LL);
LABEL_6:
    v5();
    return v3;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IAMFilterMiscFlags.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IAMFilterMiscFlags.Data4 )
  {
    v7 = (unsigned __int64)this + 128;
LABEL_15:
    v3 = 0;
    v8 = (void *)(v7 & -(__int64)(this != 0));
    if ( !a3 )
      return (unsigned int)-2147467261;
    *a3 = v8;
    v5 = *(void (**)(void))(*(_QWORD *)v8 + 8LL);
    goto LABEL_6;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IFileSinkFilter2.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IFileSinkFilter2.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IFileSinkFilter.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IFileSinkFilter.Data4 )
  {
    v7 = (unsigned __int64)this + 136;
    goto LABEL_15;
  }
  if ( *(_QWORD *)&IID_ISpecifyPropertyPages.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_ISpecifyPropertyPages.Data4 == *(_QWORD *)a2->Data4 )
  {
    v7 = (unsigned __int64)this + 144;
    goto LABEL_15;
  }
  if ( *(_QWORD *)&IID_IConfigAsfWriter.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IConfigAsfWriter.Data4 == *(_QWORD *)a2->Data4
    || *(_QWORD *)&IID_IConfigAsfWriter2.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IConfigAsfWriter2.Data4 == *(_QWORD *)a2->Data4 )
  {
    v7 = (unsigned __int64)this + 152;
    goto LABEL_15;
  }
  if ( *(_QWORD *)&IID_IPersistStream.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IPersistStream.Data4 == *(_QWORD *)a2->Data4 )
  {
    v7 = (unsigned __int64)this + 160;
    goto LABEL_15;
  }
  if ( *(_QWORD *)&IID_IWMHeaderInfo.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IWMHeaderInfo.Data4 == *(_QWORD *)a2->Data4 )
  {
    v7 = (unsigned __int64)this + 176;
    goto LABEL_15;
  }
  if ( *(_QWORD *)&IID_IWMWriterPreprocess.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IWMWriterPreprocess.Data4 == *(_QWORD *)a2->Data4 )
  {
    v7 = (unsigned __int64)this + 192;
    goto LABEL_15;
  }
  if ( *(_QWORD *)&IID_IServiceProvider.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IServiceProvider.Data4 == *(_QWORD *)a2->Data4 )
  {
    v7 = (unsigned __int64)this + 184;
    goto LABEL_15;
  }
  return CBaseFilter::NonDelegatingQueryInterface(this, a2, a3);
}

```

## disassembly

```asm
0x1800105e0  push    rbx
0x1800105e2  sub     rsp, 20h
0x1800105e6  mov     rax, [rdx]
0x1800105e9  cmp     rax, qword ptr cs:IID_IMediaSeeking.Data1
0x1800105f0  jnz     short loc_180010631
0x1800105f2  mov     rax, [rdx+8]
0x1800105f6  cmp     rax, qword ptr cs:IID_IMediaSeeking.Data4
0x1800105fd  jnz     short loc_180010631
0x1800105ff  lea     rax, [rcx+78h]
0x180010603  neg     rcx
0x180010606  sbb     rcx, rcx
0x180010609  xor     ebx, ebx
0x18001060b  and     rcx, rax
0x18001060e  test    r8, r8
0x180010611  jnz     short loc_18001061A
0x180010613  mov     ebx, 80004003h
0x180010618  jmp     short loc_180010629
0x18001061a  mov     [r8], rcx
0x18001061d  mov     rdx, [rcx]
0x180010620  mov     rax, [rdx+8]
0x180010624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010629  mov     eax, ebx
0x18001062b  add     rsp, 20h
0x18001062f  pop     rbx
0x180010630  retn
0x180010631  mov     rax, [rdx]
0x180010634  cmp     rax, qword ptr cs:IID_IAMFilterMiscFlags.Data1
0x18001063b  jnz     short loc_18001065F
0x18001063d  mov     rax, [rdx+8]
0x180010641  cmp     rax, qword ptr cs:IID_IAMFilterMiscFlags.Data4
0x180010648  jnz     short loc_18001065F
0x18001064a  lea     rax, [rcx+80h]
0x180010651  jmp     short loc_18001067F
0x180010653  mov     [r8], rcx
0x180010656  mov     rax, [rcx]
0x180010659  mov     rax, [rax+8]
0x18001065d  jmp     short loc_180010624
0x18001065f  mov     rax, [rdx]
0x180010662  cmp     rax, qword ptr cs:IID_IFileSinkFilter2.Data1
0x180010669  jnz     short loc_180010691
0x18001066b  mov     rax, [rdx+8]
0x18001066f  cmp     rax, qword ptr cs:IID_IFileSinkFilter2.Data4
0x180010676  jnz     short loc_180010691
0x180010678  lea     rax, [rcx+88h]
0x18001067f  neg     rcx
0x180010682  sbb     rcx, rcx
0x180010685  xor     ebx, ebx
0x180010687  and     rcx, rax; this
0x18001068a  test    r8, r8
0x18001068d  jnz     short loc_180010653
0x18001068f  jmp     short loc_180010613
0x180010691  mov     rax, [rdx]
0x180010694  cmp     rax, qword ptr cs:IID_IFileSinkFilter.Data1
0x18001069b  jnz     short loc_1800106AA
0x18001069d  mov     rax, [rdx+8]
0x1800106a1  cmp     rax, qword ptr cs:IID_IFileSinkFilter.Data4
0x1800106a8  jz      short loc_180010678
0x1800106aa  mov     rax, qword ptr cs:IID_ISpecifyPropertyPages.Data1
0x1800106b1  cmp     rax, [rdx]
0x1800106b4  jnz     short loc_1800106CC
0x1800106b6  mov     rax, qword ptr cs:IID_ISpecifyPropertyPages.Data4
0x1800106bd  cmp     rax, [rdx+8]
0x1800106c1  jnz     short loc_1800106CC
0x1800106c3  lea     rax, [rcx+90h]
0x1800106ca  jmp     short loc_18001067F
0x1800106cc  mov     rax, qword ptr cs:IID_IConfigAsfWriter.Data1
0x1800106d3  cmp     rax, [rdx]
0x1800106d6  jnz     short loc_1800106EE
0x1800106d8  mov     rax, qword ptr cs:IID_IConfigAsfWriter.Data4
0x1800106df  cmp     rax, [rdx+8]
0x1800106e3  jnz     short loc_1800106EE
0x1800106e5  lea     rax, [rcx+98h]
0x1800106ec  jmp     short loc_18001067F
0x1800106ee  mov     rax, qword ptr cs:IID_IConfigAsfWriter2.Data1
0x1800106f5  cmp     rax, [rdx]
0x1800106f8  jnz     short loc_180010707
0x1800106fa  mov     rax, qword ptr cs:IID_IConfigAsfWriter2.Data4
0x180010701  cmp     rax, [rdx+8]
0x180010705  jz      short loc_1800106E5
0x180010707  mov     rax, qword ptr cs:IID_IPersistStream.Data1
0x18001070e  cmp     rax, [rdx]
0x180010711  jnz     short loc_18001072C
0x180010713  mov     rax, qword ptr cs:IID_IPersistStream.Data4
0x18001071a  cmp     rax, [rdx+8]
0x18001071e  jnz     short loc_18001072C
0x180010720  lea     rax, [rcx+0A0h]
0x180010727  jmp     loc_18001067F
0x18001072c  mov     rax, qword ptr cs:IID_IWMHeaderInfo.Data1
0x180010733  cmp     rax, [rdx]
0x180010736  jnz     short loc_180010751
0x180010738  mov     rax, qword ptr cs:IID_IWMHeaderInfo.Data4
0x18001073f  cmp     rax, [rdx+8]
0x180010743  jnz     short loc_180010751
0x180010745  lea     rax, [rcx+0B0h]
0x18001074c  jmp     loc_18001067F
0x180010751  mov     rax, qword ptr cs:IID_IWMWriterPreprocess.Data1
0x180010758  cmp     rax, [rdx]
0x18001075b  jnz     short loc_180010776
0x18001075d  mov     rax, qword ptr cs:IID_IWMWriterPreprocess.Data4
0x180010764  cmp     rax, [rdx+8]
0x180010768  jnz     short loc_180010776
0x18001076a  lea     rax, [rcx+0C0h]
0x180010771  jmp     loc_18001067F
0x180010776  mov     rax, qword ptr cs:IID_IServiceProvider.Data1
0x18001077d  cmp     rax, [rdx]
0x180010780  jnz     short loc_18001079B
0x180010782  mov     rax, qword ptr cs:IID_IServiceProvider.Data4
0x180010789  cmp     rax, [rdx+8]
0x18001078d  jnz     short loc_18001079B
0x18001078f  lea     rax, [rcx+0B8h]
0x180010796  jmp     loc_18001067F
0x18001079b  add     rsp, 20h
0x18001079f  pop     rbx
0x1800107a0  jmp     ?NonDelegatingQueryInterface@CBaseFilter@@UEAAJAEBU_GUID@@PEAPEAX@Z; CBaseFilter::NonDelegatingQueryInterface(_GUID const &,void * *)
```
