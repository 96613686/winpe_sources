# VetoedRemovalUI(HWND__ *,VETO_DEVICE_COLLECTION *)

- ea: `0x180007f1c`
- end: `0x18000839c`
- name: `?VetoedRemovalUI@@YAHPEAUHWND__@@PEAUVETO_DEVICE_COLLECTION@@@Z`
- size: `1152`
- prototype: `__int64 __fastcall(HWND hWnd, struct VETO_DEVICE_COLLECTION *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180004aec`
- `0x180006eac`

## callees

- `0x180002de8`
- `0x180002e58`
- `0x180003048`
- `0x180007f1c`
- `0x180008760`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180008174`
- `KERNEL32!CloseHandle` at `0x180008367`
- `KERNEL32!CloseHandle` at `0x180008174`
- `KERNEL32!CloseHandle` at `0x180008367`
- `KERNEL32!CreateEventW` at `0x18000814c`
- `KERNEL32!CreateEventW` at `0x18000814c`
- `KERNEL32!WaitForSingleObject` at `0x180008163`
- `KERNEL32!WaitForSingleObject` at `0x180008163`
- `KERNEL32!lstrcmpW` at `0x180008093`
- `KERNEL32!lstrcmpW` at `0x180008093`
- `USER32!MessageBoxW` at `0x180008359`
- `USER32!MessageBoxW` at `0x180008359`
- `USER32!LoadStringW` at `0x1800080b9`
- `USER32!LoadStringW` at `0x1800081c4`
- `USER32!LoadStringW` at `0x180008212`
- `USER32!LoadStringW` at `0x180008255`
- `USER32!LoadStringW` at `0x1800082ab`
- `USER32!LoadStringW` at `0x1800080b9`
- `USER32!LoadStringW` at `0x1800081c4`
- `USER32!LoadStringW` at `0x180008212`
- `USER32!LoadStringW` at `0x180008255`
- `USER32!LoadStringW` at `0x1800082ab`
- `SHLWAPI!StrChrW` at `0x180007fe3`
- `SHLWAPI!StrChrW` at `0x180008132`
- `SHLWAPI!StrChrW` at `0x180007fe3`
- `SHLWAPI!StrChrW` at `0x180008132`

## pseudocode

```c
__int64 __fastcall VetoedRemovalUI(HWND hWnd, struct VETO_DEVICE_COLLECTION *a2)
{
  void *v4; // r14
  struct VETO_DEVICE_COLLECTION *v5; // rcx
  struct VETO_DEVICE_COLLECTION *v6; // rdx
  const WCHAR *v7; // r15
  int i; // eax
  const WCHAR *v9; // rbx
  PWSTR v10; // rax
  const WCHAR *v11; // rcx
  int v12; // edx
  int v13; // esi
  int v14; // r9d
  HINSTANCE v15; // rcx
  UINT v16; // edx
  int v17; // edx
  UINT v18; // edx
  PWSTR v19; // rax
  HANDLE EventW; // rax
  UINT v22; // edx
  UINT v23; // edx
  __int64 v24; // rdx
  __int64 v25; // r9
  __int64 v26; // rcx
  WCHAR *v27; // rdx
  __int64 v28; // r9
  WCHAR *v29; // rax
  WCHAR *v30; // rcx
  WCHAR Buffer[512]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Caption[256]; // [rsp+430h] [rbp+330h] BYREF
  WCHAR Text[512]; // [rsp+630h] [rbp+530h] BYREF
  WCHAR pszStart[264]; // [rsp+A30h] [rbp+930h] BYREF

  v4 = 0;
  v5 = *(struct VETO_DEVICE_COLLECTION **)a2;
  v6 = *(struct VETO_DEVICE_COLLECTION **)a2;
  v7 = 0;
  if ( v6 != a2 )
    v7 = (const WCHAR *)((char *)v6 + 16);
  for ( i = 0; v5 != a2 && i != 1; ++i )
    v5 = *(struct VETO_DEVICE_COLLECTION **)v5;
  v9 = 0;
  if ( v5 != a2 )
    v9 = (const WCHAR *)((char *)v5 + 16);
  if ( !hWnd
    && (int)StringCchPrintfW(
              pszStart,
              0x104u,
              L"Local\\VETO-%d-%d-%s",
              *((unsigned int *)a2 + 8),
              *((_DWORD *)a2 + 9),
              v9) >= 0 )
  {
    v10 = StrChrW(pszStart, 0x5Cu);
    if ( v10 )
    {
      v11 = v10 + 1;
      if ( v10 != (PWSTR)-2LL )
      {
        while ( 1 )
        {
          v19 = StrChrW(v11, 0x5Cu);
          if ( !v19 )
            break;
          *v19 = 35;
          v11 = v19;
        }
        EventW = CreateEventW(0, 0, 1, pszStart);
        v4 = EventW;
        if ( EventW )
        {
          if ( WaitForSingleObject(EventW, 0) )
          {
            CloseHandle(v4);
            return 0;
          }
        }
      }
    }
  }
  v12 = *((_DWORD *)a2 + 9);
  if ( v12 == 1 || *((_DWORD *)a2 + 9) == 2 )
    goto LABEL_19;
  if ( *((_DWORD *)a2 + 9) != 3 )
  {
    if ( *((_DWORD *)a2 + 9) == 4 )
    {
      v13 = 1600;
      goto LABEL_20;
    }
    if ( *((_DWORD *)a2 + 9) == 5 )
    {
      v13 = 1700;
      goto LABEL_20;
    }
    if ( *((_DWORD *)a2 + 9) != 7 )
    {
LABEL_19:
      v13 = 1200;
      goto LABEL_20;
    }
  }
  v13 = 1500;
LABEL_20:
  v14 = *((_DWORD *)a2 + 8);
  if ( v14 > 7 )
  {
    switch ( v14 )
    {
      case 8:
        goto LABEL_32;
      case 9:
        goto LABEL_65;
      case 10:
        goto LABEL_32;
    }
    if ( v14 != 11 )
    {
      if ( v14 == 12 )
      {
        if ( ((v12 - 3) & 0xFFFFFFFB) == 0 )
        {
          v15 = hHotPlug;
          v22 = v13 + 12;
          goto LABEL_53;
        }
      }
      else if ( v14 != 13 )
      {
LABEL_60:
        v23 = v13;
LABEL_61:
        LoadStringW(hHotPlug, v23, Buffer, 512);
        v17 = 0;
        goto LABEL_34;
      }
LABEL_65:
      v23 = v14 + v13;
      goto LABEL_61;
    }
  }
  else if ( v14 != 7 )
  {
    if ( v14 )
    {
      if ( v14 == 1 || v14 == 2 )
        goto LABEL_32;
      if ( v14 != 3 )
      {
        if ( v14 != 4 )
        {
          if ( v14 != 5 )
          {
            if ( v14 == 6 )
            {
              if ( v12 == 7 && !lstrcmpW(v9, v7) )
                v13 += 92;
              goto LABEL_32;
            }
            goto LABEL_60;
          }
LABEL_32:
          v15 = hHotPlug;
          v16 = v13 + *((_DWORD *)a2 + 8);
LABEL_33:
          LoadStringW(v15, v16, Buffer, 512);
          v17 = 1;
LABEL_34:
          DeviceCollectionFormatDeviceText((struct DEVICE_COLLECTION **)a2, v17, Buffer, 0x200u, Text);
          goto LABEL_35;
        }
        goto LABEL_64;
      }
      v15 = hHotPlug;
      v16 = v13 + 3;
      if ( v9 )
        goto LABEL_33;
      v22 = v13 + 99;
LABEL_53:
      LoadStringW(v15, v22, Text, 512);
      goto LABEL_35;
    }
    goto LABEL_65;
  }
LABEL_64:
  LoadStringW(hHotPlug, v14 + v13, Buffer, 512);
  DeviceCollectionFormatServiceText((struct DEVICE_COLLECTION **)a2, v24, Buffer, v25, Text);
LABEL_35:
  if ( *((_DWORD *)a2 + 9) != 1 )
  {
    switch ( *((_DWORD *)a2 + 9) )
    {
      case 2:
LABEL_42:
        v18 = 2257;
        goto LABEL_70;
      case 3:
        goto LABEL_68;
      case 4:
        v18 = 2264;
        goto LABEL_70;
      case 5:
        v18 = 2265;
        goto LABEL_70;
    }
    if ( *((_DWORD *)a2 + 9) != 6 )
    {
      if ( *((_DWORD *)a2 + 9) != 7 )
        goto LABEL_42;
LABEL_68:
      v18 = 2258;
      goto LABEL_70;
    }
  }
  v18 = 2254;
LABEL_70:
  LoadStringW(hHotPlug, v18, Buffer, 512);
  if ( *((_DWORD *)a2 + 9) == 1
    || *((_DWORD *)a2 + 9) == 2
    || *((_DWORD *)a2 + 9) == 3
    || (unsigned int)(*((_DWORD *)a2 + 9) - 4) > 1 )
  {
    DeviceCollectionFormatDeviceText((struct DEVICE_COLLECTION **)a2, 0, Buffer, 0x100u, Caption);
  }
  else
  {
    v26 = 2147483646;
    v27 = Buffer;
    v28 = 256;
    v29 = Caption;
    do
    {
      if ( !v26 )
        break;
      if ( !*v27 )
        break;
      *v29++ = *v27++;
      --v26;
      --v28;
    }
    while ( v28 );
    v30 = v29 - 1;
    if ( v28 )
      v30 = v29;
    *v30 = 0;
    Caption[255] = 0;
  }
  MessageBoxW(hWnd, Text, Caption, 0x50030u);
  if ( v4 )
    CloseHandle(v4);
  return 1;
}

```

## disassembly

```asm
0x180007f1c  mov     [rsp-8+arg_10], rbx
0x180007f21  push    rbp
0x180007f22  push    rsi
0x180007f23  push    rdi
0x180007f24  push    r12
0x180007f26  push    r13
0x180007f28  push    r14
0x180007f2a  push    r15
0x180007f2c  lea     rbp, [rsp-0B50h]
0x180007f34  sub     rsp, 0C50h
0x180007f3b  mov     rax, cs:__security_cookie
0x180007f42  xor     rax, rsp
0x180007f45  mov     [rbp+0B80h+var_40], rax
0x180007f4c  xor     r13d, r13d
0x180007f4f  mov     rdi, rdx
0x180007f52  mov     r12, rcx
0x180007f55  mov     r14d, r13d
0x180007f58  mov     rcx, [rdx]
0x180007f5b  mov     eax, r13d
0x180007f5e  mov     rdx, rcx
0x180007f61  cmp     rcx, rdi
0x180007f64  jz      short loc_180007F74
0x180007f66  test    eax, eax
0x180007f68  jz      short loc_180007F74
0x180007f6a  mov     rdx, [rdx]
0x180007f6d  inc     eax
0x180007f6f  cmp     rdx, rdi
0x180007f72  jnz     short loc_180007F66
0x180007f74  lea     rax, [rdx+10h]
0x180007f78  cmp     rdx, rdi
0x180007f7b  mov     r15, r13
0x180007f7e  cmovnz  r15, rax
0x180007f82  mov     eax, r13d
0x180007f85  jmp     short loc_180007F91
0x180007f87  cmp     eax, 1
0x180007f8a  jz      short loc_180007F96
0x180007f8c  mov     rcx, [rcx]
0x180007f8f  inc     eax
0x180007f91  cmp     rcx, rdi
0x180007f94  jnz     short loc_180007F87
0x180007f96  cmp     rcx, rdi
0x180007f99  lea     rax, [rcx+10h]
0x180007f9d  mov     rbx, r13
0x180007fa0  mov     esi, 5Ch ; '\'
0x180007fa5  cmovnz  rbx, rax
0x180007fa9  test    r12, r12
0x180007fac  jnz     short loc_180007FFB
0x180007fae  mov     eax, [rdi+24h]
0x180007fb1  lea     r8, aLocalVetoDDS; "Local\\VETO-%d-%d-%s"
0x180007fb8  mov     r9d, [rdi+20h]
0x180007fbc  lea     rcx, [rbp+0B80h+pszStart]; unsigned __int16 *
0x180007fc3  mov     [rsp+0C80h+var_C58], rbx
0x180007fc8  mov     edx, 104h; unsigned __int64
0x180007fcd  mov     dword ptr [rsp+0C80h+var_C60], eax
0x180007fd1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007fd6  test    eax, eax
0x180007fd8  js      short loc_180007FFB
0x180007fda  mov     edx, esi; wMatch
0x180007fdc  lea     rcx, [rbp+0B80h+pszStart]; pszStart
0x180007fe3  call    cs:__imp_StrChrW
0x180007fe9  test    rax, rax
0x180007fec  jz      short loc_180007FFB
0x180007fee  lea     rcx, [rax+2]
0x180007ff2  test    rcx, rcx
0x180007ff5  jnz     loc_180008130
0x180007ffb  mov     edx, [rdi+24h]
0x180007ffe  mov     ecx, edx
0x180008000  sub     ecx, 1
0x180008003  jz      short loc_180008033
0x180008005  sub     ecx, 1
0x180008008  jz      short loc_180008033
0x18000800a  sub     ecx, 1
0x18000800d  jz      loc_180008195
0x180008013  sub     ecx, 1
0x180008016  jz      loc_18000818B
0x18000801c  sub     ecx, 1
0x18000801f  jz      loc_180008181
0x180008025  sub     ecx, 1
0x180008028  jz      short loc_180008033
0x18000802a  cmp     ecx, 1
0x18000802d  jz      loc_180008195
0x180008033  mov     esi, 4B0h
0x180008038  mov     r9d, [rdi+20h]
0x18000803c  cmp     r9d, 7
0x180008040  jg      loc_1800081CF
0x180008046  jz      loc_18000823D
0x18000804c  mov     r8d, r9d
0x18000804f  test    r9d, r9d
0x180008052  jz      loc_180008279
0x180008058  sub     r8d, 1
0x18000805c  jz      short loc_1800080A0
0x18000805e  sub     r8d, 1
0x180008062  jz      short loc_1800080A0
0x180008064  sub     r8d, 1
0x180008068  jz      loc_18000819F
0x18000806e  sub     r8d, 1
0x180008072  jz      loc_18000823D
0x180008078  sub     r8d, 1
0x18000807c  jz      short loc_1800080A0
0x18000807e  cmp     r8d, 1
0x180008082  jnz     loc_1800081FC
0x180008088  cmp     edx, 7
0x18000808b  jnz     short loc_1800080A0
0x18000808d  mov     rdx, r15; lpString2
0x180008090  mov     rcx, rbx; lpString1
0x180008093  call    cs:__imp_lstrcmpW
0x180008099  test    eax, eax
0x18000809b  jnz     short loc_1800080A0
0x18000809d  add     esi, 5Ch ; '\'
0x1800080a0  mov     edx, [rdi+20h]
0x1800080a3  mov     ebx, 200h
0x1800080a8  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x1800080af  add     edx, esi; uID
0x1800080b1  mov     r9d, ebx; cchBufferMax
0x1800080b4  lea     r8, [rsp+0C80h+Buffer]; lpBuffer
0x1800080b9  call    cs:__imp_LoadStringW
0x1800080bf  mov     edx, 1; unsigned int
0x1800080c4  lea     rax, [rbp+0B80h+Text]
0x1800080cb  mov     r9d, ebx; unsigned int
0x1800080ce  lea     r8, [rsp+0C80h+Buffer]; unsigned __int16 *
0x1800080d3  mov     [rsp+0C80h+var_C60], rax; unsigned __int16 *
0x1800080d8  mov     rcx, rdi; struct DEVICE_COLLECTION *
0x1800080db  call    ?DeviceCollectionFormatDeviceText@@YAHPEAUDEVICE_COLLECTION@@KPEAGK1@Z; DeviceCollectionFormatDeviceText(DEVICE_COLLECTION *,ulong,ushort *,ulong,ushort *)
0x1800080e0  mov     ecx, [rdi+24h]
0x1800080e3  sub     ecx, 1
0x1800080e6  jz      loc_180008297
0x1800080ec  sub     ecx, 1
0x1800080ef  jz      short loc_18000811E
0x1800080f1  sub     ecx, 1
0x1800080f4  jz      loc_180008290
0x1800080fa  sub     ecx, 1
0x1800080fd  jz      loc_180008289
0x180008103  sub     ecx, 1
0x180008106  jz      loc_180008282
0x18000810c  sub     ecx, 1
0x18000810f  jz      loc_180008297
0x180008115  cmp     ecx, 1
0x180008118  jz      loc_180008290
0x18000811e  mov     edx, 8D1h
0x180008123  jmp     loc_18000829C
0x180008128  mov     word ptr [rax], 23h ; '#'
0x18000812d  mov     rcx, rax; pszStart
0x180008130  mov     edx, esi; wMatch
0x180008132  call    cs:__imp_StrChrW
0x180008138  test    rax, rax
0x18000813b  jnz     short loc_180008128
0x18000813d  lea     r9, [rbp+0B80h+pszStart]; lpName
0x180008144  xor     edx, edx; bManualReset
0x180008146  xor     ecx, ecx; lpEventAttributes
0x180008148  lea     r8d, [rax+1]; bInitialState
0x18000814c  call    cs:__imp_CreateEventW
0x180008152  mov     r14, rax
0x180008155  test    rax, rax
0x180008158  jz      loc_180007FFB
0x18000815e  xor     edx, edx; dwMilliseconds
0x180008160  mov     rcx, rax; hHandle
0x180008163  call    cs:__imp_WaitForSingleObject
0x180008169  test    eax, eax
0x18000816b  jz      loc_180007FFB
0x180008171  mov     rcx, r14; hObject
0x180008174  call    cs:__imp_CloseHandle
0x18000817a  xor     eax, eax
0x18000817c  jmp     loc_180008372
0x180008181  mov     esi, 6A4h
0x180008186  jmp     loc_180008038
0x18000818b  mov     esi, 640h
0x180008190  jmp     loc_180008038
0x180008195  mov     esi, 5DCh
0x18000819a  jmp     loc_180008038
0x18000819f  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x1800081a6  lea     edx, [rsi+3]
0x1800081a9  test    rbx, rbx
0x1800081ac  mov     ebx, 200h
0x1800081b1  mov     r9d, ebx; cchBufferMax
0x1800081b4  jnz     loc_1800080B4
0x1800081ba  add     edx, 60h ; '`'; uID
0x1800081bd  lea     r8, [rbp+0B80h+Text]; lpBuffer
0x1800081c4  call    cs:__imp_LoadStringW
0x1800081ca  jmp     loc_1800080E0
0x1800081cf  mov     ecx, r9d
0x1800081d2  sub     ecx, 8
0x1800081d5  jz      loc_1800080A0
0x1800081db  sub     ecx, 1
0x1800081de  jz      loc_180008279
0x1800081e4  sub     ecx, 1
0x1800081e7  jz      loc_1800080A0
0x1800081ed  sub     ecx, 1
0x1800081f0  jz      short loc_18000823D
0x1800081f2  sub     ecx, 1
0x1800081f5  jz      short loc_18000821F
0x1800081f7  cmp     ecx, 1
0x1800081fa  jz      short loc_180008279
0x1800081fc  mov     edx, esi; uID
0x1800081fe  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x180008205  lea     r8, [rsp+0C80h+Buffer]; lpBuffer
0x18000820a  mov     ebx, 200h
0x18000820f  mov     r9d, ebx; cchBufferMax
0x180008212  call    cs:__imp_LoadStringW
0x180008218  xor     edx, edx
0x18000821a  jmp     loc_1800080C4
0x18000821f  lea     eax, [rdx-3]
0x180008222  test    eax, 0FFFFFFFBh
0x180008227  jnz     short loc_180008279
0x180008229  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hHotPlug
0x180008230  lea     edx, [rsi+0Ch]
0x180008233  mov     ebx, 200h
0x180008238  mov     r9d, ebx
0x18000823b  jmp     short loc_1800081BD
0x18000823d  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x180008244  lea     edx, [r9+rsi]; uID
0x180008248  mov     ebx, 200h
0x18000824d  lea     r8, [rsp+0C80h+Buffer]; lpBuffer
0x180008252  mov     r9d, ebx; cchBufferMax
0x180008255  call    cs:__imp_LoadStringW
0x18000825b  lea     rax, [rbp+0B80h+Text]
0x180008262  mov     rcx, rdi; struct DEVICE_COLLECTION *
0x180008265  lea     r8, [rsp+0C80h+Buffer]; unsigned __int16 *
0x18000826a  mov     [rsp+0C80h+var_C60], rax; unsigned __int16 *
0x18000826f  call    ?DeviceCollectionFormatServiceText@@YAHPEAUDEVICE_COLLECTION@@KPEAGK1@Z; DeviceCollectionFormatServiceText(DEVICE_COLLECTION *,ulong,ushort *,ulong,ushort *)
0x180008274  jmp     loc_1800080E0
0x180008279  lea     edx, [r9+rsi]
0x18000827d  jmp     loc_1800081FE
0x180008282  mov     edx, 8D9h
0x180008287  jmp     short loc_18000829C
0x180008289  mov     edx, 8D8h
0x18000828e  jmp     short loc_18000829C
0x180008290  mov     edx, 8D2h
0x180008295  jmp     short loc_18000829C
0x180008297  mov     edx, 8CEh; uID
0x18000829c  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x1800082a3  lea     r8, [rsp+0C80h+Buffer]; lpBuffer
0x1800082a8  mov     r9d, ebx; cchBufferMax
0x1800082ab  call    cs:__imp_LoadStringW
0x1800082b1  mov     ecx, [rdi+24h]
0x1800082b4  sub     ecx, 1
0x1800082b7  jz      short loc_180008321
0x1800082b9  sub     ecx, 1
0x1800082bc  jz      short loc_180008321
0x1800082be  sub     ecx, 1
0x1800082c1  jz      short loc_180008321
0x1800082c3  sub     ecx, 1
0x1800082c6  jz      short loc_1800082CD
0x1800082c8  sub     ecx, 1
0x1800082cb  jnz     short loc_180008321
0x1800082cd  mov     ecx, 7FFFFFFEh
0x1800082d2  lea     rdx, [rsp+0C80h+Buffer]
0x1800082d7  mov     r9d, 100h
0x1800082dd  lea     rax, [rbp+0B80h+Caption]
0x1800082e4  test    rcx, rcx
0x1800082e7  jz      short loc_180008308
0x1800082e9  movzx   r8d, word ptr [rdx]
0x1800082ed  test    r8w, r8w
0x1800082f1  jz      short loc_180008308
0x1800082f3  mov     [rax], r8w
0x1800082f7  add     rdx, 2
0x1800082fb  add     rax, 2
0x1800082ff  dec     rcx
0x180008302  sub     r9, 1
0x180008306  jnz     short loc_1800082E4
0x180008308  test    r9, r9
0x18000830b  lea     rcx, [rax-2]
0x18000830f  cmovnz  rcx, rax
0x180008313  mov     [rcx], r13w
0x180008317  mov     [rbp+0B80h+var_652], r13w
0x18000831f  jmp     short loc_180008342
0x180008321  lea     rax, [rbp+0B80h+Caption]
0x180008328  mov     r9d, 100h; unsigned int
0x18000832e  lea     r8, [rsp+0C80h+Buffer]; unsigned __int16 *
0x180008333  mov     [rsp+0C80h+var_C60], rax; unsigned __int16 *
0x180008338  xor     edx, edx; unsigned int
0x18000833a  mov     rcx, rdi; struct DEVICE_COLLECTION *
0x18000833d  call    ?DeviceCollectionFormatDeviceText@@YAHPEAUDEVICE_COLLECTION@@KPEAGK1@Z; DeviceCollectionFormatDeviceText(DEVICE_COLLECTION *,ulong,ushort *,ulong,ushort *)
0x180008342  mov     r9d, 50030h; uType
0x180008348  lea     r8, [rbp+0B80h+Caption]; lpCaption
0x18000834f  lea     rdx, [rbp+0B80h+Text]; lpText
0x180008356  mov     rcx, r12; hWnd
0x180008359  call    cs:__imp_MessageBoxW
0x18000835f  test    r14, r14
0x180008362  jz      short loc_18000836D
0x180008364  mov     rcx, r14; hObject
0x180008367  call    cs:__imp_CloseHandle
0x18000836d  mov     eax, 1
0x180008372  mov     rcx, [rbp+0B80h+var_40]
0x180008379  xor     rcx, rsp; StackCookie
0x18000837c  call    __security_check_cookie
0x180008381  mov     rbx, [rsp+0C80h+arg_10]
0x180008389  add     rsp, 0C50h
0x180008390  pop     r15
0x180008392  pop     r14
0x180008394  pop     r13
0x180008396  pop     r12
0x180008398  pop     rdi
0x180008399  pop     rsi
0x18000839a  pop     rbp
0x18000839b  retn
```
