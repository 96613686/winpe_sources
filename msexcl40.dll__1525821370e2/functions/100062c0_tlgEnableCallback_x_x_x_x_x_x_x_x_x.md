# _tlgEnableCallback(x,x,x,x,x,x,x,x,x)

- ea: `0x100062c0`
- end: `0x10006343`
- name: `__tlgEnableCallback@36`
- size: `131`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x100062c0`
- `0x10035b40`

## pseudocode

```c
void __stdcall _tlgEnableCallback(
        LPCGUID SourceId,
        ULONG IsEnabled,
        int Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        _QWORD *CallbackContext)
{
  int v7; // ecx
  int v8; // ecx
  void (__thiscall *v9)(_DWORD, LPCGUID, ULONG, int, _DWORD, _DWORD, int, _DWORD, PEVENT_FILTER_DESCRIPTOR, _DWORD); // esi

  if ( CallbackContext )
  {
    if ( IsEnabled )
    {
      if ( IsEnabled == 1 )
      {
        if ( (_BYTE)Level )
          v7 = (unsigned __int8)Level + 1;
        else
          v7 = 256;
        *(_DWORD *)CallbackContext = v7;
        CallbackContext[1] = MatchAnyKeyword;
        v8 = MatchAllKeyword;
        CallbackContext[2] = MatchAllKeyword;
        goto LABEL_10;
      }
    }
    else
    {
      *(_DWORD *)CallbackContext = 0;
    }
    v8 = MatchAllKeyword;
LABEL_10:
    v9 = (void (__thiscall *)(_DWORD, LPCGUID, ULONG, int, _DWORD, _DWORD, int, _DWORD, PEVENT_FILTER_DESCRIPTOR, _DWORD))*((_DWORD *)CallbackContext + 8);
    if ( v9 )
      v9(
        v9,
        SourceId,
        IsEnabled,
        Level,
        MatchAnyKeyword,
        HIDWORD(MatchAnyKeyword),
        v8,
        HIDWORD(MatchAllKeyword),
        FilterData,
        *((_DWORD *)CallbackContext + 9));
  }
}

```

## disassembly

```asm
0x100062c0  mov     edi, edi
0x100062c2  push    ebp
0x100062c3  mov     ebp, esp
0x100062c5  and     esp, 0FFFFFFF8h
0x100062c8  mov     eax, [ebp+CallbackContext]
0x100062cb  push    ebx
0x100062cc  push    esi
0x100062cd  test    eax, eax
0x100062cf  jz      short loc_1000633B
0x100062d1  mov     ecx, [ebp+IsEnabled]
0x100062d4  mov     ebx, dword ptr [ebp+MatchAllKeyword+4]
0x100062d7  mov     edx, [ebp+Level]
0x100062da  sub     ecx, 0
0x100062dd  jz      short loc_1000630C
0x100062df  sub     ecx, 1
0x100062e2  jnz     short loc_10006312
0x100062e4  test    dl, dl
0x100062e6  jz      short loc_100062EE
0x100062e8  movzx   ecx, dl
0x100062eb  inc     ecx
0x100062ec  jmp     short loc_100062F3
0x100062ee  mov     ecx, 100h
0x100062f3  mov     [eax], ecx
0x100062f5  mov     ecx, dword ptr [ebp+MatchAnyKeyword]
0x100062f8  mov     [eax+8], ecx
0x100062fb  mov     ecx, dword ptr [ebp+MatchAnyKeyword+4]
0x100062fe  mov     [eax+0Ch], ecx
0x10006301  mov     ecx, dword ptr [ebp+MatchAllKeyword]
0x10006304  mov     [eax+10h], ecx
0x10006307  mov     [eax+14h], ebx
0x1000630a  jmp     short loc_10006315
0x1000630c  mov     dword ptr [eax], 0
0x10006312  mov     ecx, dword ptr [ebp+MatchAllKeyword]
0x10006315  mov     esi, [eax+20h]
0x10006318  test    esi, esi
0x1000631a  jz      short loc_1000633B
0x1000631c  push    dword ptr [eax+24h]
0x1000631f  push    [ebp+FilterData]
0x10006322  push    ebx
0x10006323  push    ecx
0x10006324  push    dword ptr [ebp+MatchAnyKeyword+4]
0x10006327  mov     ecx, esi
0x10006329  push    dword ptr [ebp+MatchAnyKeyword]
0x1000632c  push    edx
0x1000632d  push    [ebp+IsEnabled]
0x10006330  push    [ebp+SourceId]
0x10006333  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10006339  call    esi
0x1000633b  pop     esi
0x1000633c  pop     ebx
0x1000633d  mov     esp, ebp
0x1000633f  pop     ebp
0x10006340  retn    24h ; '$'
```
