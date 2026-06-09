# IASVssWriter::EnableVssWriter(void)

- ea: `0x18000c340`
- end: `0x18000c4db`
- name: `?EnableVssWriter@IASVssWriter@@UEAAJXZ`
- size: `411`
- prototype: `__int64 __fastcall(IASVssWriter *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800071ac`
- `0x18000c340`
- `0x18000d990`
- `0x180010010`

## import_xrefs

- `VSSAPI!CreateWriter` at `0x18000c37c`
- `VSSAPI!CreateWriter` at `0x18000c37c`

## string_xrefs

- `0x18000c42e`: `CVssWriter::Initialize failed with 0x%x`
- `0x18000c4a7`: `CVssWriter::Subscribe(VSS_SM_BACKUP_EVENTS_FLAG) failed with 0x%x`
- `0x18000c38f`: `NPS VSS Writer`

## pseudocode

```c
__int64 __fastcall IASVssWriter::EnableVssWriter(IASVssWriter *this)
{
  char *v2; // rcx
  _QWORD *v3; // rdi
  int Writer; // ebx
  __int64 v5; // rcx
  __int64 (__fastcall *v6)(__int64, __int128 *, const wchar_t *, _QWORD, _DWORD, _DWORD, int, int, int, int, int, _BYTE); // rax
  __int64 v7; // rdx
  __int64 result; // rax
  __int64 v9; // rcx
  __int128 v10; // [rsp+70h] [rbp-28h] BYREF

  v2 = (char *)this - 16;
  v3 = v2 + 8;
  if ( *((_QWORD *)v2 + 1) )
  {
    Writer = -2147467259;
    goto LABEL_6;
  }
  Writer = CreateWriter(v2, v2 + 8);
  if ( Writer < 0 )
  {
LABEL_6:
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    {
      return (unsigned int)Writer;
    }
    WppDbgPrint("CVssWriter::Initialize failed with 0x%x");
    v7 = 17;
LABEL_10:
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_51d954edd6d93851aca784e64cc7fb39_Traceguids);
    return (unsigned int)Writer;
  }
  v5 = *v3;
  v6 = *(__int64 (__fastcall **)(__int64, __int128 *, const wchar_t *, _QWORD, _DWORD, _DWORD, int, int, int, int, int, _BYTE))(*(_QWORD *)*v3 + 24LL);
  v10 = xmmword_1800157A8;
  Writer = v6(v5, &v10, L"NPS VSS Writer", 0, 0, 0, 2, 2, 1, 60000, 1, 0);
  if ( Writer < 0 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 16LL))(*v3);
    *v3 = 0;
    goto LABEL_6;
  }
  v9 = *((_QWORD *)this - 1);
  if ( !v9 )
  {
    Writer = -2147467259;
    goto LABEL_15;
  }
  result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v9 + 32LL))(v9, 0, 6);
  Writer = result;
  if ( (int)result < 0 )
  {
LABEL_15:
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    {
      return (unsigned int)Writer;
    }
    WppDbgPrint("CVssWriter::Subscribe(VSS_SM_BACKUP_EVENTS_FLAG) failed with 0x%x");
    v7 = 18;
    goto LABEL_10;
  }
  *((_DWORD *)this + 13) = 1;
  return result;
}

```

## disassembly

```asm
0x18000c340  mov     rax, rsp
0x18000c343  mov     [rax+8], rbx
0x18000c347  mov     [rax+10h], rsi
0x18000c34b  push    rdi
0x18000c34c  sub     rsp, 90h
0x18000c353  mov     rsi, rcx
0x18000c356  movaps  xmmword ptr [rax-18h], xmm6
0x18000c35a  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c35e  lea     rdi, [rcx+8]
0x18000c362  cmp     qword ptr [rdi], 0
0x18000c366  jz      short loc_18000C372
0x18000c368  mov     ebx, 80004005h
0x18000c36d  jmp     loc_18000C40D
0x18000c372  movups  xmm6, cs:xmmword_1800157A8
0x18000c379  mov     rdx, rdi
0x18000c37c  call    cs:__imp_CreateWriter
0x18000c382  mov     ebx, eax
0x18000c384  test    eax, eax
0x18000c386  js      loc_18000C40D
0x18000c38c  mov     rcx, [rdi]
0x18000c38f  lea     r8, aNpsVssWriter; "NPS VSS Writer"
0x18000c396  mov     [rsp+98h+var_40], 0
0x18000c39b  lea     rdx, [rsp+98h+var_28]
0x18000c3a0  mov     [rsp+98h+var_48], 1
0x18000c3a8  xor     r9d, r9d
0x18000c3ab  mov     [rsp+98h+var_50], 0EA60h
0x18000c3b3  mov     rax, [rcx]
0x18000c3b6  mov     [rsp+98h+var_58], 1
0x18000c3be  mov     [rsp+98h+var_60], 2
0x18000c3c6  mov     [rsp+98h+var_68], 2
0x18000c3ce  mov     rax, [rax+18h]
0x18000c3d2  mov     [rsp+98h+var_70], 0
0x18000c3da  movdqa  [rsp+98h+var_28], xmm6
0x18000c3e0  mov     [rsp+98h+var_78], 0
0x18000c3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3ed  mov     ebx, eax
0x18000c3ef  test    eax, eax
0x18000c3f1  jns     short loc_18000C409
0x18000c3f3  mov     rcx, [rdi]
0x18000c3f6  mov     rax, [rcx]
0x18000c3f9  mov     rax, [rax+10h]
0x18000c3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c402  mov     qword ptr [rdi], 0
0x18000c409  test    ebx, ebx
0x18000c40b  jns     short loc_18000C45E
0x18000c40d  mov     rax, cs:WPP_GLOBAL_Control
0x18000c414  lea     rcx, WPP_GLOBAL_Control
0x18000c41b  cmp     rax, rcx
0x18000c41e  jz      short loc_18000C45A
0x18000c420  cmp     byte ptr [rax+19h], 2
0x18000c424  jb      short loc_18000C45A
0x18000c426  test    byte ptr [rax+1Ch], 10h
0x18000c42a  jz      short loc_18000C45A
0x18000c42c  mov     edx, ebx
0x18000c42e  lea     rcx, aCvsswriterInit; "CVssWriter::Initialize failed with 0x%x"
0x18000c435  call    WppDbgPrint
0x18000c43a  mov     edx, 11h
0x18000c43f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c446  lea     r8, WPP_51d954edd6d93851aca784e64cc7fb39_Traceguids
0x18000c44d  mov     [rsp+98h+var_78], ebx
0x18000c451  mov     rcx, [rcx+10h]
0x18000c455  call    WPP_SF_sd
0x18000c45a  mov     eax, ebx
0x18000c45c  jmp     short loc_18000C4C1
0x18000c45e  mov     rcx, [rsi-8]
0x18000c462  test    rcx, rcx
0x18000c465  jnz     short loc_18000C46E
0x18000c467  mov     ebx, 80004005h
0x18000c46c  jmp     short loc_18000C486
0x18000c46e  mov     rax, [rcx]
0x18000c471  xor     edx, edx
0x18000c473  mov     rax, [rax+20h]
0x18000c477  lea     r8d, [rdx+6]
0x18000c47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c480  mov     ebx, eax
0x18000c482  test    eax, eax
0x18000c484  jns     short loc_18000C4BA
0x18000c486  mov     rax, cs:WPP_GLOBAL_Control
0x18000c48d  lea     rcx, WPP_GLOBAL_Control
0x18000c494  cmp     rax, rcx
0x18000c497  jz      short loc_18000C45A
0x18000c499  cmp     byte ptr [rax+19h], 2
0x18000c49d  jb      short loc_18000C45A
0x18000c49f  test    byte ptr [rax+1Ch], 10h
0x18000c4a3  jz      short loc_18000C45A
0x18000c4a5  mov     edx, ebx
0x18000c4a7  lea     rcx, aCvsswriterSubs; "CVssWriter::Subscribe(VSS_SM_BACKUP_EVE"...
0x18000c4ae  call    WppDbgPrint
0x18000c4b3  mov     edx, 12h
0x18000c4b8  jmp     short loc_18000C43F
0x18000c4ba  mov     dword ptr [rsi+34h], 1
0x18000c4c1  lea     r11, [rsp+98h+var_8]
0x18000c4c9  mov     rbx, [r11+10h]
0x18000c4cd  mov     rsi, [r11+18h]
0x18000c4d1  movaps  xmm6, xmmword ptr [r11-10h]
0x18000c4d6  mov     rsp, r11
0x18000c4d9  pop     rdi
0x18000c4da  retn
```
