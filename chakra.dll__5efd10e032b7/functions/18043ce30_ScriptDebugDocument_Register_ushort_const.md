# ScriptDebugDocument::Register(ushort const *)

- ea: `0x18043ce30`
- end: `0x18043d3fa`
- name: `?Register@ScriptDebugDocument@@QEAAJPEBG@Z`
- size: `1482`
- prototype: `__int64 __fastcall(ScriptDebugDocument *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18041f684`

## callees

- `0x18011a1e4`
- `0x18011c600`
- `0x180154664`
- `0x1802a4330`
- `0x18032c7d4`
- `0x18043c2f0`
- `0x18043c4d0`
- `0x18043c6a8`
- `0x18043c95c`
- `0x18043ca68`
- `0x18043ce30`
- `0x18043d450`
- `0x18059b8f8`
- `0x18059bb9c`
- `0x1805cd010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18043d02b`
- `msvcrt!wcsrchr` at `0x18043d042`
- `msvcrt!wcsrchr` at `0x18043d02b`
- `msvcrt!wcsrchr` at `0x18043d042`
- `msvcrt!wcscpy_s` at `0x18043d062`
- `msvcrt!wcscpy_s` at `0x18043d062`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18043cee8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18043cee8`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall ScriptDebugDocument::Register(ScriptDebugDocument *this, const unsigned __int16 *a2)
{
  __int64 v3; // rax
  __int64 v4; // r13
  SourceContextInfo **v5; // rdx
  bool IsDynamic; // si
  char v7; // r12
  __int64 v8; // r8
  wchar_t *v9; // r14
  _QWORD *v10; // r15
  HRESULT LatestPDM; // eax
  __int64 v12; // rcx
  int DebugApplicationCoreNoRef; // ebx
  const unsigned __int16 *v14; // rbx
  unsigned __int16 *v15; // rax
  int v16; // r9d
  wchar_t *v17; // rsi
  wchar_t *v19; // rax
  struct IDebugApplication64 *v20; // rcx
  int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rbx
  SourceContextInfo *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  wchar_t *v32; // r8
  bool v33; // [rsp+48h] [rbp-29h]
  struct IDebugApplicationNode *v34; // [rsp+50h] [rbp-21h] BYREF
  __int64 v35; // [rsp+58h] [rbp-19h] BYREF
  struct IDebugDocumentContext *v36; // [rsp+60h] [rbp-11h] BYREF
  struct IDebugApplicationNode *v37; // [rsp+68h] [rbp-9h] BYREF
  struct IDebugApplication64 *v38; // [rsp+70h] [rbp-1h] BYREF
  SourceContextInfo **v39; // [rsp+78h] [rbp+7h]
  ScriptEngine *v40; // [rsp+80h] [rbp+Fh]
  __int64 v41; // [rsp+88h] [rbp+17h]

  v41 = -2;
  v3 = *((_QWORD *)this + 7);
  v40 = *(ScriptEngine **)(v3 + 24);
  v4 = *(_QWORD *)(v3 + 8);
  v39 = *(SourceContextInfo ***)(v4 + 104);
  IsDynamic = SourceContextInfo::IsDynamic(*v39);
  v33 = IsDynamic;
  v7 = *((_BYTE *)v5 + 36) & 1;
  LODWORD(v35) = *(_DWORD *)(v8 + 964);
  v9 = 0;
  v37 = 0;
  v34 = 0;
  v36 = 0;
  v10 = (_QWORD *)((char *)this + 48);
  if ( v7 )
  {
    DebugApplicationCoreNoRef = 0;
    v17 = 0;
    goto LABEL_24;
  }
  if ( (unsigned int)ShouldUseLocalPDM() )
    LatestPDM = LoadLatestPDM(
                  &GUID_83b8bca6_687c_11d0_a405_00aa0060275c,
                  &GUID_c4c7363c_20fd_47f9_bd82_4855e0150871,
                  (void **)this + 6);
  else
    LatestPDM = CoCreateInstance(
                  &GUID_83b8bca6_687c_11d0_a405_00aa0060275c,
                  0,
                  1u,
                  &GUID_c4c7363c_20fd_47f9_bd82_4855e0150871,
                  (LPVOID *)this + 6);
  DebugApplicationCoreNoRef = LatestPDM;
  if ( !LatestPDM )
  {
    v14 = L"script block";
    if ( a2 )
      v14 = a2;
    v15 = (unsigned __int16 *)Memory::AllocateArray<Memory::HeapAllocator,unsigned short,0>(
                                v12,
                                Memory::HeapAllocator::NoThrowAlloc,
                                255);
    if ( IsDynamic )
    {
      v9 = v15;
      if ( v15 )
      {
        v17 = (wchar_t *)v14;
        ScriptDebugDocument::GetFormattedTitle(this, v14, v15, v16);
LABEL_17:
        v38 = 0;
        DebugApplicationCoreNoRef = ScriptEngine::GetDebugApplicationCoreNoRef(v40, &v38);
        if ( DebugApplicationCoreNoRef < 0 )
          goto LABEL_62;
        v21 = (v33 ? 1 : 8) | 4;
        if ( !(_DWORD)v35 )
          v21 = v33 ? 1 : 8;
        DebugApplicationCoreNoRef = (*(__int64 (__fastcall **)(_QWORD, struct IDebugApplication64 *, wchar_t *, wchar_t *, int))(*(_QWORD *)*v10 + 24LL))(
                                      *v10,
                                      v38,
                                      v17,
                                      v9,
                                      v21);
        if ( DebugApplicationCoreNoRef < 0 )
          goto LABEL_62;
        DebugApplicationCoreNoRef = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, _DWORD, char *))(*(_QWORD *)*v10 + 80LL))(
                                      *v10,
                                      0,
                                      *(unsigned int *)(v4 + 8),
                                      (char *)v40 + 56,
                                      0,
                                      (char *)this + 72);
        if ( DebugApplicationCoreNoRef < 0 )
          goto LABEL_62;
        v5 = v39;
LABEL_24:
        if ( ScriptDebugDocument::GetDocumentContext(this, *((_DWORD *)v5 + 5), 1u, &v36) >= 0 )
        {
          v38 = 0;
          if ( ((int (__fastcall *)(struct IDebugDocumentContext *, struct IDebugApplication64 **))v36->lpVtbl->GetDocument)(
                 v36,
                 &v38) >= 0 )
          {
            v35 = 0;
            if ( ((__int64 (__fastcall *)(struct IDebugApplication64 *, GUID *, __int64 *))v38->lpVtbl->QueryInterface)(
                   v38,
                   &GUID_51973c22_cb0c_11d0_b5c9_00a0244a0e7a,
                   &v35) >= 0 )
            {
              v22 = *(_QWORD *)(v4 + 96);
              v23 = v22 + 56;
              if ( !v22 )
                v23 = 64;
              *(_QWORD *)v23 = v35;
            }
            if ( v35 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          }
          v20 = v38;
          if ( v38 )
            ((void (__fastcall *)(struct IDebugApplication64 *))v38->lpVtbl->Release)(v38);
        }
        if ( !v7 )
        {
          DebugApplicationCoreNoRef = ScriptDebugDocument::AddText(this);
          if ( DebugApplicationCoreNoRef >= 0 )
          {
            if ( (*(unsigned int (__fastcall **)(_QWORD, struct IDebugApplicationNode **))(*(_QWORD *)*v10 + 128LL))(
                   *v10,
                   &v34) )
            {
LABEL_60:
              DebugApplicationCoreNoRef = ScriptDebugDocument::AttachNode(this, v34, v37);
              if ( DebugApplicationCoreNoRef >= 0 )
                *((_BYTE *)this + 84) = 1;
              goto LABEL_62;
            }
            v24 = *(_QWORD *)(v4 + 152);
            if ( v24 )
            {
              v25 = *(_QWORD *)(v24 + 96);
              if ( v25 )
              {
                if ( v25 != 8 )
                {
                  v26 = *(_QWORD *)(v25 - 8 + 48);
                  if ( v26 )
                    (*(void (__fastcall **)(__int64, struct IDebugApplicationNode **))(*(_QWORD *)v26 + 128LL))(
                      v26,
                      &v37);
                }
              }
              if ( v37 )
                goto LABEL_48;
              if ( !v33 || (*(_BYTE *)(*(_QWORD *)(v24 + 104) + 36LL) & 1) != 0 )
                goto LABEL_47;
              v38 = 0;
              ScriptEngine::GetDebugApplicationCoreNoRef(v40, &v38);
              ((void (__fastcall *)(struct IDebugApplication64 *, struct IDebugApplicationNode **))v38->lpVtbl->GetRootNode)(
                v38,
                &v37);
            }
            if ( v37 )
            {
LABEL_48:
              v35 = 0;
              if ( !(**(unsigned int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v10)(
                      *v10,
                      &GUID_51973c20_cb0c_11d0_b5c9_00a0244a0e7a,
                      &v35) )
              {
                v28 = operator new<Memory::NoThrowHeapAllocator>(
                        32,
                        &Memory::HeapAllocator::Instance,
                        v27,
                        Memory::HeapAllocator::NoThrowAlloc);
                if ( v28 )
                {
                  v29 = *v39;
                  v30 = v35;
                  *(_QWORD *)v28 = &ScriptDocumentProviderBridge::`vftable';
                  *(_DWORD *)(v28 + 8) = 0;
                  *(_QWORD *)(v28 + 16) = v30;
                  *(_QWORD *)(v28 + 24) = v29;
                  if ( v30 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
                  _InterlockedIncrement((volatile signed __int32 *)(v28 + 8));
                }
                else
                {
                  v28 = 0;
                }
                v39 = (SourceContextInfo **)v28;
                v31 = v28;
                if ( !v28 )
                  v31 = v35;
                ((void (__fastcall *)(struct IDebugApplicationNode *, __int64))v34->lpVtbl->SetDocumentProvider)(
                  v34,
                  v31);
                if ( v28 )
                  ScriptDocumentProviderBridge::Release((ScriptDocumentProviderBridge *)v28);
              }
              if ( v35 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
              goto LABEL_60;
            }
LABEL_47:
            ScriptDebugDocument::DbgGetRootApplicationNode(this, &v37);
            goto LABEL_48;
          }
        }
LABEL_62:
        if ( v33 )
        {
          if ( v9 )
          {
            v32 = v9;
LABEL_67:
            Memory::DeleteArray<Memory::HeapAllocator,unsigned short>(v20, 255, v32);
          }
        }
        else if ( v17 )
        {
          v32 = v17;
          goto LABEL_67;
        }
        if ( v36 )
        {
          ((void (__fastcall *)(struct IDebugDocumentContext *))v36->lpVtbl->Release)(v36);
          v36 = 0;
        }
        if ( v34 )
        {
          ((void (__fastcall *)(struct IDebugApplicationNode *))v34->lpVtbl->Release)(v34);
          v34 = 0;
        }
        if ( v37 )
          ((void (__fastcall *)(struct IDebugApplicationNode *))v37->lpVtbl->Release)(v37);
        return (unsigned int)DebugApplicationCoreNoRef;
      }
    }
    else
    {
      v17 = v15;
      if ( v15 )
      {
        v9 = (wchar_t *)v14;
        v19 = wcsrchr(v14, 0x2Fu);
        if ( v19 || (v19 = wcsrchr(v14, 0x5Cu)) != 0 )
          v14 = v19 + 1;
        wcscpy_s(v17, 0xFFu, v14);
        goto LABEL_17;
      }
    }
    return 2147942414LL;
  }
  return (unsigned int)DebugApplicationCoreNoRef;
}

```

## disassembly

```asm
0x18043ce30  mov     rax, rsp
0x18043ce33  mov     [rax+10h], rdx
0x18043ce37  mov     [rax+8], rcx
0x18043ce3b  push    rbp
0x18043ce3c  push    rsi
0x18043ce3d  push    rdi
0x18043ce3e  push    r12
0x18043ce40  push    r13
0x18043ce42  push    r14
0x18043ce44  push    r15
0x18043ce46  lea     rbp, [rax-5Fh]
0x18043ce4a  sub     rsp, 90h
0x18043ce51  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x18043ce59  mov     [rax+18h], rbx
0x18043ce5d  mov     rdi, [rbp+57h+arg_0]
0x18043ce61  mov     rax, [rdi+38h]
0x18043ce65  mov     r8, [rax+18h]
0x18043ce69  mov     [rbp+57h+var_48], r8
0x18043ce6d  mov     r13, [rax+8]
0x18043ce71  mov     rdx, [r13+68h]
0x18043ce75  mov     [rbp+57h+var_50], rdx
0x18043ce79  mov     rcx, [rdx]; this
0x18043ce7c  call    ?IsDynamic@SourceContextInfo@@QEBA_NXZ; SourceContextInfo::IsDynamic(void)
0x18043ce81  mov     sil, al
0x18043ce84  mov     [rbp+57h+var_80], al
0x18043ce87  mov     r12b, [rdx+24h]
0x18043ce8b  and     r12b, 1
0x18043ce8f  mov     eax, [r8+3C4h]
0x18043ce96  mov     dword ptr [rbp+57h+var_70], eax
0x18043ce99  mov     r14d, 0
0x18043ce9f  mov     [rbp+57h+var_60], r14
0x18043cea3  mov     [rbp+57h+var_78], r14
0x18043cea7  mov     [rbp+57h+var_68], r14
0x18043ceab  lea     r15, [rdi+30h]
0x18043ceaf  jnz     loc_18043D111
0x18043ceb5  call    ?ShouldUseLocalPDM@@YAHXZ; ShouldUseLocalPDM(void)
0x18043ceba  lea     rcx, _GUID_83b8bca6_687c_11d0_a405_00aa0060275c; struct _GUID *
0x18043cec1  test    eax, eax
0x18043cec3  jz      short loc_18043CED6
0x18043cec5  mov     r8, r15; void **
0x18043cec8  lea     rdx, _GUID_c4c7363c_20fd_47f9_bd82_4855e0150871; struct _GUID *
0x18043cecf  call    ?LoadLatestPDM@@YAJAEBU_GUID@@0PEAPEAX@Z; LoadLatestPDM(_GUID const &,_GUID const &,void * *)
0x18043ced4  jmp     short loc_18043CEF4
0x18043ced6  mov     [rsp+0C0h+ppv], r15; ppv
0x18043cedb  lea     r9, _GUID_c4c7363c_20fd_47f9_bd82_4855e0150871; riid
0x18043cee2  xor     edx, edx; pUnkOuter
0x18043cee4  lea     r8d, [rdx+1]; dwClsContext
0x18043cee8  call    cs:__imp_CoCreateInstance
0x18043ceef  nop     dword ptr [rax+rax+00h]
0x18043cef4  mov     ebx, eax
0x18043cef6  test    eax, eax
0x18043cef8  jz      short loc_18043CF47
0x18043cefa  mov     rcx, [rbp+57h+var_68]
0x18043cefe  test    rcx, rcx
0x18043cf01  jz      short loc_18043CF13
0x18043cf03  mov     rax, [rcx]
0x18043cf06  mov     rax, [rax+10h]
0x18043cf0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043cf0f  mov     [rbp+57h+var_68], r14
0x18043cf13  mov     rcx, [rbp+57h+var_78]
0x18043cf17  test    rcx, rcx
0x18043cf1a  jz      short loc_18043CF2C
0x18043cf1c  mov     rax, [rcx]
0x18043cf1f  mov     rax, [rax+10h]
0x18043cf23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043cf28  mov     [rbp+57h+var_78], r14
0x18043cf2c  mov     rcx, [rbp+57h+var_60]
0x18043cf30  test    rcx, rcx
0x18043cf33  jz      short loc_18043CF42
0x18043cf35  mov     rax, [rcx]
0x18043cf38  mov     rax, [rax+10h]
0x18043cf3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043cf41  nop
0x18043cf42  jmp     loc_18043D3DC
0x18043cf47  mov     rax, [rbp+57h+Str]
0x18043cf4b  lea     rbx, aScriptBlock; "script block"
0x18043cf52  test    rax, rax
0x18043cf55  cmovnz  rbx, rax
0x18043cf59  mov     r8d, 0FFh
0x18043cf5f  lea     rdx, ?NoThrowAlloc@HeapAllocator@Memory@@QEAAPEAD_K@Z; Memory::HeapAllocator::NoThrowAlloc(unsigned __int64)
0x18043cf66  call    ??$AllocateArray@UHeapAllocator@Memory@@G$0A@@Memory@@YAPEAGPEAUHeapAllocator@0@P810@EAAPEAD_K@Z1@Z; Memory::AllocateArray<Memory::HeapAllocator,ushort,0>(Memory::HeapAllocator *,char * (Memory::HeapAllocator::*)(unsigned __int64),unsigned __int64)
0x18043cf6b  test    sil, sil
0x18043cf6e  jz      short loc_18043CFC6
0x18043cf70  mov     r14, rax
0x18043cf73  test    rax, rax
0x18043cf76  jnz     short loc_18043CFB0
0x18043cf78  mov     rcx, [rbp+57h+var_68]
0x18043cf7c  test    rcx, rcx
0x18043cf7f  jz      short loc_18043CF91
0x18043cf81  mov     rax, [rcx]
0x18043cf84  mov     rax, [rax+10h]
0x18043cf88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043cf8d  mov     [rbp+57h+var_68], r14
0x18043cf91  mov     rcx, [rbp+57h+var_78]
0x18043cf95  test    rcx, rcx
0x18043cf98  jz      short loc_18043CFAE
0x18043cf9a  mov     rax, [rcx]
0x18043cf9d  mov     rax, [rax+10h]
0x18043cfa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043cfa6  mov     [rbp+57h+var_78], 0
0x18043cfae  jmp     short loc_18043D000
0x18043cfb0  mov     rsi, rbx
0x18043cfb3  mov     r8, rax; unsigned __int16 *
0x18043cfb6  mov     rdx, rbx; unsigned __int16 *
0x18043cfb9  mov     rcx, rdi; this
0x18043cfbc  call    ?GetFormattedTitle@ScriptDebugDocument@@QEAAXPEBGPEAGH@Z; ScriptDebugDocument::GetFormattedTitle(ushort const *,ushort *,int)
0x18043cfc1  jmp     loc_18043D06E
0x18043cfc6  mov     rsi, rax
0x18043cfc9  test    rax, rax
0x18043cfcc  jnz     short loc_18043D020
0x18043cfce  mov     rcx, [rbp+57h+var_68]
0x18043cfd2  test    rcx, rcx
0x18043cfd5  jz      short loc_18043CFE7
0x18043cfd7  mov     rax, [rcx]
0x18043cfda  mov     rax, [rax+10h]
0x18043cfde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043cfe3  mov     [rbp+57h+var_68], r14
0x18043cfe7  mov     rcx, [rbp+57h+var_78]
0x18043cfeb  test    rcx, rcx
0x18043cfee  jz      short loc_18043D000
0x18043cff0  mov     rax, [rcx]
0x18043cff3  mov     rax, [rax+10h]
0x18043cff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043cffc  mov     [rbp+57h+var_78], r14
0x18043d000  mov     rcx, [rbp+57h+var_60]
0x18043d004  test    rcx, rcx
0x18043d007  jz      short loc_18043D016
0x18043d009  mov     rax, [rcx]
0x18043d00c  mov     rax, [rax+10h]
0x18043d010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043d015  nop
0x18043d016  mov     eax, 8007000Eh
0x18043d01b  jmp     loc_18043D3DE
0x18043d020  mov     r14, rbx
0x18043d023  mov     edx, 2Fh ; '/'; Ch
0x18043d028  mov     rcx, rbx; Str
0x18043d02b  call    cs:__imp_wcsrchr
0x18043d032  nop     dword ptr [rax+rax+00h]
0x18043d037  test    rax, rax
0x18043d03a  jnz     short loc_18043D053
0x18043d03c  lea     edx, [rax+5Ch]; Ch
0x18043d03f  mov     rcx, rbx; Str
0x18043d042  call    cs:__imp_wcsrchr
0x18043d049  nop     dword ptr [rax+rax+00h]
0x18043d04e  test    rax, rax
0x18043d051  jz      short loc_18043D057
0x18043d053  lea     rbx, [rax+2]
0x18043d057  mov     r8, rbx; Source
0x18043d05a  mov     edx, 0FFh; SizeInWords
0x18043d05f  mov     rcx, rsi; Destination
0x18043d062  call    cs:__imp_wcscpy_s
0x18043d069  nop     dword ptr [rax+rax+00h]
0x18043d06e  mov     [rbp+57h+var_58], 0
0x18043d076  lea     rdx, [rbp+57h+var_58]; struct IDebugApplication64 **
0x18043d07a  mov     rcx, [rbp+57h+var_48]; this
0x18043d07e  call    ?GetDebugApplicationCoreNoRef@ScriptEngine@@QEAAJPEAPEAUIDebugApplication64@@@Z; ScriptEngine::GetDebugApplicationCoreNoRef(IDebugApplication64 * *)
0x18043d083  mov     ebx, eax
0x18043d085  test    eax, eax
0x18043d087  js      loc_18043D369
0x18043d08d  mov     al, [rbp+57h+var_80]
0x18043d090  neg     al
0x18043d092  sbb     edx, edx
0x18043d094  and     edx, 0FFFFFFF9h
0x18043d097  add     edx, 8
0x18043d09a  mov     r10, [r15]
0x18043d09d  mov     rax, [r10]
0x18043d0a0  mov     ecx, edx
0x18043d0a2  or      ecx, 4
0x18043d0a5  cmp     dword ptr [rbp+57h+var_70], 0
0x18043d0a9  cmovz   ecx, edx
0x18043d0ac  mov     dword ptr [rsp+0C0h+ppv], ecx
0x18043d0b0  mov     r9, r14
0x18043d0b3  mov     r8, rsi
0x18043d0b6  mov     rdx, [rbp+57h+var_58]
0x18043d0ba  mov     rcx, r10
0x18043d0bd  mov     rax, [rax+18h]
0x18043d0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043d0c6  mov     ebx, eax
0x18043d0c8  test    eax, eax
0x18043d0ca  js      loc_18043D369
0x18043d0d0  mov     r10, [r15]
0x18043d0d3  mov     rax, [r10]
0x18043d0d6  lea     rcx, [rdi+48h]
0x18043d0da  mov     r9, [rbp+57h+var_48]
0x18043d0de  add     r9, 38h ; '8'
0x18043d0e2  mov     [rsp+28h], rcx
0x18043d0e7  mov     dword ptr [rsp+0C0h+ppv], 0
0x18043d0ef  mov     r8d, [r13+8]
0x18043d0f3  xor     edx, edx
0x18043d0f5  mov     rcx, r10
0x18043d0f8  mov     rax, [rax+50h]
0x18043d0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043d101  mov     ebx, eax
0x18043d103  test    eax, eax
0x18043d105  js      loc_18043D369
0x18043d10b  mov     rdx, [rbp+57h+var_50]
0x18043d10f  jmp     short loc_18043D116
0x18043d111  mov     ebx, r14d
0x18043d114  xor     esi, esi
0x18043d116  lea     r9, [rbp+57h+var_68]; struct IDebugDocumentContext **
0x18043d11a  mov     r8d, 1; unsigned int
0x18043d120  mov     edx, [rdx+14h]; unsigned int
0x18043d123  mov     rcx, rdi; this
0x18043d126  call    ?GetDocumentContext@ScriptDebugDocument@@QEAAJKKPEAPEAUIDebugDocumentContext@@@Z; ScriptDebugDocument::GetDocumentContext(ulong,ulong,IDebugDocumentContext * *)
0x18043d12b  test    eax, eax
0x18043d12d  js      loc_18043D1C0
0x18043d133  mov     [rbp+57h+var_58], 0
0x18043d13b  mov     rcx, [rbp+57h+var_68]
0x18043d13f  mov     rax, [rcx]
0x18043d142  lea     rdx, [rbp+57h+var_58]
0x18043d146  mov     rax, [rax+18h]
0x18043d14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043d14f  test    eax, eax
0x18043d151  js      short loc_18043D1AA
0x18043d153  mov     [rbp+57h+var_70], 0
0x18043d15b  mov     rcx, [rbp+57h+var_58]
0x18043d15f  mov     rax, [rcx]
0x18043d162  lea     r8, [rbp+57h+var_70]
0x18043d166  lea     rdx, _GUID_51973c22_cb0c_11d0_b5c9_00a0244a0e7a
0x18043d16d  mov     rax, [rax]
0x18043d170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043d175  test    eax, eax
0x18043d177  js      short loc_18043D194
0x18043d179  mov     rax, [r13+60h]
0x18043d17d  lea     rcx, [rax+38h]
0x18043d181  mov     edx, 40h ; '@'
0x18043d186  test    rax, rax
0x18043d189  cmovz   rcx, rdx
0x18043d18d  mov     rax, [rbp+57h+var_70]
0x18043d191  mov     [rcx], rax
0x18043d194  mov     rcx, [rbp+57h+var_70]
0x18043d198  test    rcx, rcx
0x18043d19b  jz      short loc_18043D1AA
0x18043d19d  mov     rax, [rcx]
0x18043d1a0  mov     rax, [rax+10h]
0x18043d1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043d1a9  nop
0x18043d1aa  mov     rcx, [rbp+57h+var_58]
0x18043d1ae  test    rcx, rcx
0x18043d1b1  jz      short loc_18043D1C0
0x18043d1b3  mov     rax, [rcx]
0x18043d1b6  mov     rax, [rax+10h]
0x18043d1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043d1bf  nop
0x18043d1c0  test    r12b, r12b
0x18043d1c3  jnz     loc_18043D369
0x18043d1c9  mov     rcx, rdi; this
0x18043d1cc  call    ?AddText@ScriptDebugDocument@@AEAAJXZ; ScriptDebugDocument::AddText(void)
0x18043d1d1  mov     ebx, eax
0x18043d1d3  test    eax, eax
0x18043d1d5  js      loc_18043D369
0x18043d1db  mov     rcx, [r15]
0x18043d1de  mov     rax, [rcx]
0x18043d1e1  lea     rdx, [rbp+57h+var_78]
0x18043d1e5  mov     rax, [rax+80h]
0x18043d1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043d1f1  test    eax, eax
0x18043d1f3  jnz     loc_18043D34F
0x18043d1f9  mov     rbx, [r13+98h]
0x18043d200  test    rbx, rbx
0x18043d203  jz      short loc_18043D273
0x18043d205  mov     rax, [rbx+60h]
0x18043d209  test    rax, rax
0x18043d20c  jz      short loc_18043D233
0x18043d20e  lea     rcx, [rax-8]
0x18043d212  test    rcx, rcx
0x18043d215  jz      short loc_18043D233
0x18043d217  mov     rcx, [rcx+30h]
0x18043d21b  test    rcx, rcx
0x18043d21e  jz      short loc_18043D233
0x18043d220  mov     rax, [rcx]
0x18043d223  lea     rdx, [rbp+57h+var_60]
0x18043d227  mov     rax, [rax+80h]
0x18043d22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043d233  cmp     [rbp+57h+var_60], 0
0x18043d238  jnz     short loc_18043D286
0x18043d23a  cmp     [rbp+57h+var_80], 0
0x18043d23e  jz      short loc_18043D27A
0x18043d240  mov     rax, [rbx+68h]
0x18043d244  test    byte ptr [rax+24h], 1
0x18043d248  jnz     short loc_18043D27A
0x18043d24a  mov     [rbp+57h+var_58], 0
0x18043d252  lea     rdx, [rbp+57h+var_58]; struct IDebugApplication64 **
0x18043d256  mov     rcx, [rbp+57h+var_48]; this
0x18043d25a  call    ?GetDebugApplicationCoreNoRef@ScriptEngine@@QEAAJPEAPEAUIDebugApplication64@@@Z; ScriptEngine::GetDebugApplicationCoreNoRef(IDebugApplication64 * *)
0x18043d25f  mov     rcx, [rbp+57h+var_58]
0x18043d263  mov     rax, [rcx]
0x18043d266  lea     rdx, [rbp+57h+var_60]
0x18043d26a  mov     rax, [rax+60h]
0x18043d26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043d273  cmp     [rbp+57h+var_60], 0
0x18043d278  jnz     short loc_18043D286
0x18043d27a  lea     rdx, [rbp+57h+var_60]; struct IDebugApplicationNode **
0x18043d27e  mov     rcx, rdi; this
0x18043d281  call    ?DbgGetRootApplicationNode@ScriptDebugDocument@@QEAAJPEAPEAUIDebugApplicationNode@@@Z; ScriptDebugDocument::DbgGetRootApplicationNode(IDebugApplicationNode * *)
0x18043d286  mov     [rbp+57h+var_70], 0
0x18043d28e  mov     rcx, [r15]
0x18043d291  mov     rax, [rcx]
0x18043d294  lea     r8, [rbp+57h+var_70]
0x18043d298  lea     rdx, _GUID_51973c20_cb0c_11d0_b5c9_00a0244a0e7a
  ... truncated ...
```
