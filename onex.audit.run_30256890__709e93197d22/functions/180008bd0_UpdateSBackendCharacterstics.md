# UpdateSBackendCharacterstics

- ea: `0x180008bd0`
- end: `0x180008d33`
- name: `UpdateSBackendCharacterstics`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800137f0`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180008bd0`
- `0x180008d40`
- `0x1800214f0`

## pseudocode

```c
__int64 __fastcall UpdateSBackendCharacterstics(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // esi
  _QWORD *v6; // rcx
  unsigned int v7; // edi
  unsigned int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx

  v5 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 20LL);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 55, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (*(_BYTE *)(a3 + 8) & 0x10) != 0 )
  {
    *(_DWORD *)(a1 + 16) = *(_DWORD *)(a3 + 28);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = *(_DWORD *)(*(_QWORD *)(a1 + 32) + 20LL);
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 17) & 0x800) != 0 )
    WPP_SF_(v6[7], 115, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  v8 = EapEndSession((EAP_SESSIONID *)(a1 + 32));
  v9 = v8;
  if ( !v8 )
    goto LABEL_13;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 116, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v7, v8);
LABEL_13:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v10[7], 117, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v9);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v9 )
  {
    if ( v10 == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)v10 + 68) & 1) != 0 )
    {
      WPP_SF_dd(v10[7], 56, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v5, v9);
      v10 = WPP_GLOBAL_Control;
    }
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x800) != 0 )
    WPP_SF_D(v10[7], 57, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180008bd0  push    rbx
0x180008bd2  push    rbp
0x180008bd3  push    rsi
0x180008bd4  push    rdi
0x180008bd5  sub     rsp, 38h
0x180008bd9  mov     rax, [rcx+8]
0x180008bdd  mov     rdi, r8
0x180008be0  mov     rbx, rcx
0x180008be3  mov     esi, [rax+14h]
0x180008be6  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bed  lea     rbp, WPP_GLOBAL_Control
0x180008bf4  cmp     rcx, rbp
0x180008bf7  jz      short loc_180008C1E
0x180008bf9  test    dword ptr [rcx+44h], 800h
0x180008c00  jz      short loc_180008C1E
0x180008c02  mov     rcx, [rcx+38h]
0x180008c06  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180008c0d  mov     edx, 37h ; '7'
0x180008c12  call    WPP_SF_
0x180008c17  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c1e  test    byte ptr [rdi+8], 10h
0x180008c22  jz      short loc_180008C31
0x180008c24  mov     eax, [rdi+1Ch]
0x180008c27  mov     [rbx+10h], eax
0x180008c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c31  mov     rax, [rbx+20h]
0x180008c35  mov     edi, [rax+14h]
0x180008c38  cmp     rcx, rbp
0x180008c3b  jz      short loc_180008C5B
0x180008c3d  test    dword ptr [rcx+44h], 800h
0x180008c44  jz      short loc_180008C5B
0x180008c46  mov     rcx, [rcx+38h]
0x180008c4a  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180008c51  mov     edx, 73h ; 's'
0x180008c56  call    WPP_SF_
0x180008c5b  lea     rcx, [rbx+20h]
0x180008c5f  call    EapEndSession
0x180008c64  mov     ebx, eax
0x180008c66  test    eax, eax
0x180008c68  jz      short loc_180008C9C
0x180008c6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c71  cmp     rcx, rbp
0x180008c74  jz      loc_180008D28
0x180008c7a  test    byte ptr [rcx+44h], 1
0x180008c7e  jz      short loc_180008CA3
0x180008c80  mov     rcx, [rcx+38h]
0x180008c84  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180008c8b  mov     edx, 74h ; 't'
0x180008c90  mov     [rsp+58h+var_38], eax
0x180008c94  mov     r9d, edi
0x180008c97  call    WPP_SF_dd
0x180008c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ca3  cmp     rcx, rbp
0x180008ca6  jz      short loc_180008CD0
0x180008ca8  test    dword ptr [rcx+44h], 800h
0x180008caf  jz      short loc_180008CD0
0x180008cb1  mov     rcx, [rcx+38h]
0x180008cb5  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180008cbc  mov     edx, 75h ; 'u'
0x180008cc1  mov     r9d, ebx
0x180008cc4  call    WPP_SF_D
0x180008cc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cd0  test    ebx, ebx
0x180008cd2  jz      short loc_180008D02
0x180008cd4  cmp     rcx, rbp
0x180008cd7  jz      short loc_180008D28
0x180008cd9  test    byte ptr [rcx+44h], 1
0x180008cdd  jz      short loc_180008D02
0x180008cdf  mov     rcx, [rcx+38h]
0x180008ce3  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180008cea  mov     edx, 38h ; '8'
0x180008cef  mov     [rsp+58h+var_38], ebx
0x180008cf3  mov     r9d, esi
0x180008cf6  call    WPP_SF_dd
0x180008cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d02  cmp     rcx, rbp
0x180008d05  jz      short loc_180008D28
0x180008d07  test    dword ptr [rcx+44h], 800h
0x180008d0e  jz      short loc_180008D28
0x180008d10  mov     rcx, [rcx+38h]
0x180008d14  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180008d1b  mov     edx, 39h ; '9'
0x180008d20  mov     r9d, ebx
0x180008d23  call    WPP_SF_D
0x180008d28  mov     eax, ebx
0x180008d2a  add     rsp, 38h
0x180008d2e  pop     rdi
0x180008d2f  pop     rsi
0x180008d30  pop     rbp
0x180008d31  pop     rbx
0x180008d32  retn
```
