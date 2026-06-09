# CImportExportCallback::OnAepImportComplete(ulong,_DEVPROPERTY * const,long)

- ea: `0x1400187a0`
- end: `0x140018876`
- name: `?OnAepImportComplete@CImportExportCallback@@UEAAJKQEAU_DEVPROPERTY@@J@Z`
- size: `214`
- prototype: `__int64 __fastcall(CImportExportCallback *this, unsigned int, struct _DEVPROPERTY *const, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000ceec`
- `0x1400187a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140018863`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140018863`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140018839`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140018839`

## pseudocode

```c
__int64 __fastcall CImportExportCallback::OnAepImportComplete(
        CImportExportCallback *this,
        unsigned int a2,
        struct _DEVPROPERTY *const a3,
        int a4)
{
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rcx
  unsigned int v11; // ebx

  if ( a4 < 0 && (a2 || a3) )
    return (unsigned int)-2147024809;
  if ( a2 )
  {
    if ( a3 )
      goto LABEL_6;
    return (unsigned int)-2147024809;
  }
  if ( a3 )
    return (unsigned int)-2147024809;
LABEL_6:
  v8 = *((_DWORD *)this + 26);
  if ( v8 && (a2 || a3) )
    return (unsigned int)-2147024809;
  v9 = 0;
  v10 = 0;
  if ( a2 )
  {
    while ( a3[v10].CompKey.Key.pid != 2
         || DEVPKEY_Aep_ContainerId != *(_QWORD *)&a3[v10].CompKey.Key.fmtid.Data1
         || *(_QWORD *)a3[v10].CompKey.Key.fmtid.Data4 != 0xC5D430B359BE8B8CuLL )
    {
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= a2 )
        goto LABEL_18;
    }
    v9 = 1;
  }
LABEL_18:
  if ( !v8 && !v9 )
    return (unsigned int)-2147024809;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_DWORD *)this + 22) )
    v11 = OnAepImportCompleteStub(a2, a3, a4, *((void **)this + 5));
  else
    v11 = -2140930029;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return v11;
}

```

## disassembly

```asm
0x1400187a0  push    rbx
0x1400187a2  push    rbp
0x1400187a3  push    rsi
0x1400187a4  push    rdi
0x1400187a5  push    r14
0x1400187a7  sub     rsp, 20h
0x1400187ab  mov     r14d, r9d
0x1400187ae  mov     rbx, r8
0x1400187b1  mov     edi, edx
0x1400187b3  mov     rbp, rcx
0x1400187b6  test    r9d, r9d
0x1400187b9  jns     short loc_1400187C4
0x1400187bb  test    edx, edx
0x1400187bd  jnz     short loc_14001881E
0x1400187bf  test    rbx, rbx
0x1400187c2  jnz     short loc_14001881E
0x1400187c4  test    edi, edi
0x1400187c6  jz      short loc_140018819
0x1400187c8  test    rbx, rbx
0x1400187cb  jz      short loc_14001881E
0x1400187cd  mov     r8d, [rcx+68h]
0x1400187d1  test    r8d, r8d
0x1400187d4  jz      short loc_1400187DF
0x1400187d6  test    edi, edi
0x1400187d8  jnz     short loc_14001881E
0x1400187da  test    rbx, rbx
0x1400187dd  jnz     short loc_14001881E
0x1400187df  xor     r9d, r9d
0x1400187e2  xor     ecx, ecx
0x1400187e4  test    edi, edi
0x1400187e6  jz      short loc_14001882B
0x1400187e8  mov     r10, cs:qword_1400215D0
0x1400187ef  mov     r11, cs:DEVPKEY_Aep_ContainerId
0x1400187f6  lea     rdx, [rcx+rcx*2]
0x1400187fa  add     rdx, rdx
0x1400187fd  cmp     dword ptr [rbx+rdx*8+10h], 2
0x140018802  jnz     short loc_140018811
0x140018804  cmp     r11, [rbx+rdx*8]
0x140018808  jnz     short loc_140018811
0x14001880a  cmp     r10, [rbx+rdx*8+8]
0x14001880f  jz      short loc_140018825
0x140018811  inc     ecx
0x140018813  cmp     ecx, edi
0x140018815  jb      short loc_1400187F6
0x140018817  jmp     short loc_14001882B
0x140018819  test    rbx, rbx
0x14001881c  jz      short loc_1400187CD
0x14001881e  mov     ebx, 80070057h
0x140018823  jmp     short loc_140018869
0x140018825  mov     r9d, 1
0x14001882b  test    r8d, r8d
0x14001882e  jnz     short loc_140018835
0x140018830  test    r9d, r9d
0x140018833  jz      short loc_14001881E
0x140018835  lea     rcx, [rbp+30h]; lpCriticalSection
0x140018839  call    cs:__imp_EnterCriticalSection
0x14001883f  cmp     dword ptr [rbp+58h], 0
0x140018843  jz      short loc_14001885A
0x140018845  mov     r9, [rbp+28h]; void *
0x140018849  mov     r8d, r14d; int
0x14001884c  mov     rdx, rbx; struct _DEVPROPERTY *
0x14001884f  mov     ecx, edi; unsigned int
0x140018851  call    ?OnAepImportCompleteStub@@YAJKQEAU_DEVPROPERTY@@JPEAX@Z; OnAepImportCompleteStub(ulong,_DEVPROPERTY * const,long,void *)
0x140018856  mov     ebx, eax
0x140018858  jmp     short loc_14001885F
0x14001885a  mov     ebx, 80640013h
0x14001885f  lea     rcx, [rbp+30h]; lpCriticalSection
0x140018863  call    cs:__imp_LeaveCriticalSection
0x140018869  mov     eax, ebx
0x14001886b  add     rsp, 20h
0x14001886f  pop     r14
0x140018871  pop     rdi
0x140018872  pop     rsi
0x140018873  pop     rbp
0x140018874  pop     rbx
0x140018875  retn
```
