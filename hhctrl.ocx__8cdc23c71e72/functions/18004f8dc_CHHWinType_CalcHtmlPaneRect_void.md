# CHHWinType::CalcHtmlPaneRect(void)

- ea: `0x18004f8dc`
- end: `0x18004fa0d`
- name: `?CalcHtmlPaneRect@CHHWinType@@QEAAXXZ`
- size: `305`
- prototype: `void __fastcall(CHHWinType *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180050158`
- `0x18006eaf4`
- `0x18007236c`

## callees

- `0x180006708`
- `0x18004f8dc`

## import_xrefs

- `USER32!CopyRect` at `0x18004f93d`
- `USER32!CopyRect` at `0x18004f93d`
- `USER32!GetClientRect` at `0x18004f8f0`
- `USER32!GetClientRect` at `0x18004f99a`
- `USER32!GetClientRect` at `0x18004f8f0`
- `USER32!GetClientRect` at `0x18004f99a`
- `USER32!GetSystemMetrics` at `0x18004f9b4`
- `USER32!GetSystemMetrics` at `0x18004f9b4`
- `USER32!GetWindowRect` at `0x18004f911`
- `USER32!GetWindowRect` at `0x18004f911`

## pseudocode

```c
void __fastcall CHHWinType::CalcHtmlPaneRect(CHHWinType *this)
{
  int v2; // ebx
  int v3; // ecx
  bool v4; // zf
  HWND v5; // rcx
  int v6; // esi
  int v7; // edx

  GetClientRect(*((HWND *)this + 8), (LPRECT)((char *)this + 116));
  if ( !(unsigned int)IsValidWindow(*((HWND *)this + 11))
    || (GetWindowRect(*((HWND *)this + 11), (LPRECT)this + 33),
        *((_DWORD *)this + 30) += *((_DWORD *)this + 135) - *((_DWORD *)this + 133),
        !*((_DWORD *)this + 140)) )
  {
LABEL_7:
    if ( !*((_DWORD *)this + 43) && (*((_DWORD *)this + 5) & 0x4000) == 0 )
    {
      v5 = (HWND)*((_QWORD *)this + 12);
      if ( v5 )
        GetClientRect(v5, (LPRECT)this + 32);
      v6 = *((_DWORD *)this + 130) - *((_DWORD *)this + 128);
      if ( *((_QWORD *)this + 40) )
        *((_DWORD *)this + 29) += GetSystemMetrics(32) + v6;
      else
        *((_DWORD *)this + 29) += v6;
    }
    goto LABEL_14;
  }
  v2 = *((_DWORD *)this + 139) - *((_DWORD *)this + 137);
  CopyRect((LPRECT)this + 34, (const RECT *)((char *)this + 116));
  if ( !v2 )
    v2 = 100;
  v3 = v2 + *((_DWORD *)this + 137);
  v4 = *((_DWORD *)this + 43) == 0;
  *((_DWORD *)this + 139) = v3;
  *((_DWORD *)this + 30) = v3;
  if ( v4 )
  {
    *((_DWORD *)this + 136) += *((_DWORD *)this + 130) - *((_DWORD *)this + 128);
    goto LABEL_7;
  }
LABEL_14:
  v4 = *((_QWORD *)this + 80) == 0;
  v7 = *(_DWORD *)((char *)this + (*((_DWORD *)this + 140) != 0 ? 0x1AC : 0) + 120);
  *((_DWORD *)this + 129) = v7;
  if ( !v4 )
    *((_DWORD *)this + 129) = v7 + *((_DWORD *)this + 164);
  *((_DWORD *)this + 131) = *((_DWORD *)this + 32);
}

```

## disassembly

```asm
0x18004f8dc  push    rbx
0x18004f8de  push    rbp
0x18004f8df  push    rsi
0x18004f8e0  push    rdi
0x18004f8e1  sub     rsp, 28h
0x18004f8e5  mov     rdi, rcx
0x18004f8e8  lea     rdx, [rcx+74h]; lpRect
0x18004f8ec  mov     rcx, [rcx+40h]; hWnd
0x18004f8f0  call    cs:__imp_GetClientRect
0x18004f8f6  mov     rcx, [rdi+58h]; HWND
0x18004f8fa  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x18004f8ff  test    eax, eax
0x18004f901  jz      short loc_18004F975
0x18004f903  mov     rcx, [rdi+58h]; hWnd
0x18004f907  lea     rbx, [rdi+210h]
0x18004f90e  mov     rdx, rbx; lpRect
0x18004f911  call    cs:__imp_GetWindowRect
0x18004f917  mov     eax, [rbx+0Ch]
0x18004f91a  sub     eax, [rbx+4]
0x18004f91d  add     [rdi+78h], eax
0x18004f920  cmp     dword ptr [rdi+230h], 0
0x18004f927  jz      short loc_18004F975
0x18004f929  lea     rsi, [rdi+220h]
0x18004f930  mov     ebx, [rsi+0Ch]
0x18004f933  lea     rdx, [rdi+74h]; lprcSrc
0x18004f937  sub     ebx, [rsi+4]
0x18004f93a  mov     rcx, rsi; lprcDst
0x18004f93d  call    cs:__imp_CopyRect
0x18004f943  mov     ecx, [rdi+224h]
0x18004f949  test    ebx, ebx
0x18004f94b  mov     eax, 64h ; 'd'
0x18004f950  cmovz   ebx, eax
0x18004f953  add     ecx, ebx
0x18004f955  cmp     dword ptr [rdi+0ACh], 0
0x18004f95c  mov     [rdi+22Ch], ecx
0x18004f962  mov     [rdi+78h], ecx
0x18004f965  jnz     short loc_18004F9C5
0x18004f967  mov     eax, [rdi+208h]
0x18004f96d  sub     eax, [rdi+200h]
0x18004f973  add     [rsi], eax
0x18004f975  cmp     dword ptr [rdi+0ACh], 0
0x18004f97c  jnz     short loc_18004F9C5
0x18004f97e  test    dword ptr [rdi+14h], 4000h
0x18004f985  jnz     short loc_18004F9C5
0x18004f987  mov     rcx, [rdi+60h]; hWnd
0x18004f98b  lea     rbx, [rdi+200h]
0x18004f992  test    rcx, rcx
0x18004f995  jz      short loc_18004F9A0
0x18004f997  mov     rdx, rbx; lpRect
0x18004f99a  call    cs:__imp_GetClientRect
0x18004f9a0  mov     esi, [rbx+8]
0x18004f9a3  sub     esi, [rbx]
0x18004f9a5  cmp     qword ptr [rdi+140h], 0
0x18004f9ad  jz      short loc_18004F9C2
0x18004f9af  mov     ecx, 20h ; ' '; nIndex
0x18004f9b4  call    cs:__imp_GetSystemMetrics
0x18004f9ba  lea     ecx, [rax+rsi]
0x18004f9bd  add     [rdi+74h], ecx
0x18004f9c0  jmp     short loc_18004F9C5
0x18004f9c2  add     [rdi+74h], esi
0x18004f9c5  mov     eax, [rdi+230h]
0x18004f9cb  neg     eax
0x18004f9cd  sbb     rcx, rcx
0x18004f9d0  and     ecx, 1ACh
0x18004f9d6  cmp     qword ptr [rdi+280h], 0
0x18004f9de  mov     edx, [rcx+rdi+78h]
0x18004f9e2  mov     [rdi+204h], edx
0x18004f9e8  jz      short loc_18004F9F8
0x18004f9ea  mov     ecx, [rdi+290h]
0x18004f9f0  add     ecx, edx
0x18004f9f2  mov     [rdi+204h], ecx
0x18004f9f8  mov     eax, [rdi+80h]
0x18004f9fe  mov     [rdi+20Ch], eax
0x18004fa04  add     rsp, 28h
0x18004fa08  pop     rdi
0x18004fa09  pop     rsi
0x18004fa0a  pop     rbp
0x18004fa0b  pop     rbx
0x18004fa0c  retn
```
