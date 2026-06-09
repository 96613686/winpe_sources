# CComponentData::_ScopePaneAddLogSet(HWND__ *)

- ea: `0x180008958`
- end: `0x1800089f9`
- name: `?_ScopePaneAddLogSet@CComponentData@@AEAAJPEAUHWND__@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(CComponentData *__hidden this, HWND hWnd)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007990`

## callees

- `0x180006fc0`
- `0x1800071d0`
- `0x180008958`
- `0x180008b70`
- `0x180016084`

## pseudocode

```c
__int64 __fastcall CComponentData::_ScopePaneAddLogSet(CComponentData *this, HWND hWnd)
{
  CLogSet *v2; // rdi
  unsigned int v3; // esi
  struct CLogInfo *v4; // rbx
  struct CLogInfo **v7; // rbx
  const wchar_t *v8; // rdx
  __int64 result; // rax

  v2 = (CLogSet *)*((_QWORD *)this + 10);
  v3 = 0;
  v4 = 0;
  while ( 1 )
  {
    if ( !v2 )
      goto LABEL_13;
    if ( *((_QWORD *)v2 + 5) == *((_QWORD *)this + 142) )
      break;
    v2 = (CLogSet *)*((_QWORD *)v2 + 1);
  }
  v7 = (struct CLogInfo **)((char *)v2 + 136);
  if ( (*((_BYTE *)this + 56) & 0x10) != 0
    && *v7
    && (v8 = (const wchar_t *)(((unsigned __int64)*v7 + 32) & -(__int64)(*((_WORD *)*v7 + 16) != 0))) != 0 )
  {
    CComponentData::SetServerFocus(this, v8);
  }
  else
  {
    CComponentData::_UpdateCurFocusSystemRoot(this);
  }
  result = CLogSet::MergeLogInfos(v2, hWnd);
  v3 = result;
  if ( (int)result >= 0 )
  {
    v4 = *v7;
LABEL_13:
    while ( v4 )
    {
      CComponentData::_AddLogInfoToScopePane(this, v4);
      v4 = (struct CLogInfo *)*((_QWORD *)v4 + 1);
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180008958  push    rbx
0x18000895a  push    rbp
0x18000895b  push    rsi
0x18000895c  push    rdi
0x18000895d  push    r14
0x18000895f  sub     rsp, 20h
0x180008963  mov     rdi, [rcx+50h]
0x180008967  xor     esi, esi
0x180008969  xor     ebx, ebx
0x18000896b  mov     r14, rdx
0x18000896e  mov     rbp, rcx
0x180008971  test    rdi, rdi
0x180008974  jz      short loc_1800089E7
0x180008976  mov     rax, [rcx+470h]
0x18000897d  cmp     [rdi+28h], rax
0x180008981  jz      short loc_180008989
0x180008983  mov     rdi, [rdi+8]
0x180008987  jmp     short loc_180008971
0x180008989  test    byte ptr [rcx+38h], 10h
0x18000898d  lea     rbx, [rdi+88h]
0x180008994  jz      short loc_1800089BA
0x180008996  mov     rcx, [rbx]
0x180008999  test    rcx, rcx
0x18000899c  jz      short loc_1800089BA
0x18000899e  add     rcx, 20h ; ' '
0x1800089a2  movzx   eax, word ptr [rcx]
0x1800089a5  neg     ax
0x1800089a8  sbb     rdx, rdx
0x1800089ab  and     rdx, rcx; pszSrc
0x1800089ae  jz      short loc_1800089BA
0x1800089b0  mov     rcx, rbp; this
0x1800089b3  call    ?SetServerFocus@CComponentData@@QEAAXPEBG@Z; CComponentData::SetServerFocus(ushort const *)
0x1800089b8  jmp     short loc_1800089C2
0x1800089ba  mov     rcx, rbp; this
0x1800089bd  call    ?_UpdateCurFocusSystemRoot@CComponentData@@AEAAXXZ; CComponentData::_UpdateCurFocusSystemRoot(void)
0x1800089c2  mov     rdx, r14; hWnd
0x1800089c5  mov     rcx, rdi; this
0x1800089c8  call    ?MergeLogInfos@CLogSet@@QEAAJPEAUHWND__@@@Z; CLogSet::MergeLogInfos(HWND__ *)
0x1800089cd  mov     esi, eax
0x1800089cf  test    eax, eax
0x1800089d1  js      short loc_1800089EE
0x1800089d3  mov     rbx, [rbx]
0x1800089d6  jmp     short loc_1800089E7
0x1800089d8  mov     rdx, rbx; struct CLogInfo *
0x1800089db  mov     rcx, rbp; this
0x1800089de  call    ?_AddLogInfoToScopePane@CComponentData@@AEAAJPEAVCLogInfo@@@Z; CComponentData::_AddLogInfoToScopePane(CLogInfo *)
0x1800089e3  mov     rbx, [rbx+8]
0x1800089e7  test    rbx, rbx
0x1800089ea  jnz     short loc_1800089D8
0x1800089ec  mov     eax, esi
0x1800089ee  add     rsp, 20h
0x1800089f2  pop     r14
0x1800089f4  pop     rdi
0x1800089f5  pop     rsi
0x1800089f6  pop     rbp
0x1800089f7  pop     rbx
0x1800089f8  retn
```
