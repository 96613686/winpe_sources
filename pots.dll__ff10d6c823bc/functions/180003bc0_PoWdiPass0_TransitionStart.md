# PoWdiPass0_TransitionStart

- ea: `0x180003bc0`
- end: `0x180003cac`
- name: `PoWdiPass0_TransitionStart`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800024e8`
- `0x180003bc0`

## pseudocode

```c
__int64 __fastcall PoWdiPass0_TransitionStart(struct _EVENT_RECORD *a1, __int64 a2)
{
  __int64 result; // rax
  int v5; // [rsp+40h] [rbp+18h] BYREF
  int v6; // [rsp+48h] [rbp+20h] BYREF

  v5 = 0;
  v6 = 0;
  result = PoWdiGetULongProperty(a1, (ULONGLONG)L"Reason", (BYTE *)&v5);
  if ( (_DWORD)result )
  {
    result = PoWdiGetULongProperty(a1, (ULONGLONG)L"Flags", (BYTE *)&v6);
    if ( (_DWORD)result )
    {
      if ( v5 > 6 )
      {
        switch ( v5 )
        {
          case 7:
            *(_DWORD *)(a2 + 4) |= 0x400u;
            break;
          case 11:
            *(_DWORD *)(a2 + 4) |= 0x200000u;
            break;
          case 12:
            *(_DWORD *)(a2 + 4) |= 0x400000u;
            break;
          case 13:
            *(_DWORD *)(a2 + 4) |= 0x800000u;
            break;
          case 14:
            *(_DWORD *)(a2 + 4) |= 0x1000000u;
            break;
        }
      }
      else if ( v5 == 6 )
      {
        *(_DWORD *)(a2 + 4) |= 0x200u;
      }
      else if ( v5 )
      {
        if ( v5 == 1 )
        {
          *(_DWORD *)(a2 + 4) |= 0x40u;
        }
        else if ( v5 == 2 )
        {
          *(_DWORD *)(a2 + 4) |= 0x80u;
        }
        else if ( (unsigned int)(v5 - 4) <= 1 )
        {
          *(_DWORD *)(a2 + 4) |= 0x100u;
        }
      }
      else
      {
        result = 16;
        if ( v6 == 4 )
          result = 32;
        *(_DWORD *)(a2 + 4) |= result;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003bc0  mov     rax, rsp
0x180003bc3  mov     [rax+8], rbx
0x180003bc7  push    rdi
0x180003bc8  sub     rsp, 20h
0x180003bcc  mov     rbx, rdx
0x180003bcf  mov     dword ptr [rax+18h], 0
0x180003bd6  lea     rdx, aReason; "Reason"
0x180003bdd  mov     dword ptr [rax+20h], 0
0x180003be4  lea     r8, [rax+18h]
0x180003be8  mov     rdi, rcx
0x180003beb  call    PoWdiGetULongProperty
0x180003bf0  test    eax, eax
0x180003bf2  jz      loc_180003CA1
0x180003bf8  lea     r8, [rsp+28h+arg_18]
0x180003bfd  mov     rcx, rdi
0x180003c00  lea     rdx, aFlags; "Flags"
0x180003c07  call    PoWdiGetULongProperty
0x180003c0c  test    eax, eax
0x180003c0e  jz      loc_180003CA1
0x180003c14  mov     ecx, [rsp+28h+arg_10]
0x180003c18  cmp     ecx, 6
0x180003c1b  jg      short loc_180003C67
0x180003c1d  jz      short loc_180003C60
0x180003c1f  test    ecx, ecx
0x180003c21  jz      short loc_180003C4B
0x180003c23  sub     ecx, 1
0x180003c26  jz      short loc_180003C45
0x180003c28  sub     ecx, 1
0x180003c2b  jz      short loc_180003C3E
0x180003c2d  sub     ecx, 2
0x180003c30  jz      short loc_180003C37
0x180003c32  cmp     ecx, 1
0x180003c35  jnz     short loc_180003CA1
0x180003c37  bts     dword ptr [rbx+4], 8
0x180003c3c  jmp     short loc_180003CA1
0x180003c3e  bts     dword ptr [rbx+4], 7
0x180003c43  jmp     short loc_180003CA1
0x180003c45  or      dword ptr [rbx+4], 40h
0x180003c49  jmp     short loc_180003CA1
0x180003c4b  cmp     [rsp+28h+arg_18], 4
0x180003c50  mov     eax, 10h
0x180003c55  lea     edx, [rax+10h]
0x180003c58  cmovz   eax, edx
0x180003c5b  or      [rbx+4], eax
0x180003c5e  jmp     short loc_180003CA1
0x180003c60  bts     dword ptr [rbx+4], 9
0x180003c65  jmp     short loc_180003CA1
0x180003c67  sub     ecx, 7
0x180003c6a  jz      short loc_180003C9C
0x180003c6c  sub     ecx, 4
0x180003c6f  jz      short loc_180003C95
0x180003c71  sub     ecx, 1
0x180003c74  jz      short loc_180003C8E
0x180003c76  sub     ecx, 1
0x180003c79  jz      short loc_180003C87
0x180003c7b  cmp     ecx, 1
0x180003c7e  jnz     short loc_180003CA1
0x180003c80  bts     dword ptr [rbx+4], 18h
0x180003c85  jmp     short loc_180003CA1
0x180003c87  bts     dword ptr [rbx+4], 17h
0x180003c8c  jmp     short loc_180003CA1
0x180003c8e  bts     dword ptr [rbx+4], 16h
0x180003c93  jmp     short loc_180003CA1
0x180003c95  bts     dword ptr [rbx+4], 15h
0x180003c9a  jmp     short loc_180003CA1
0x180003c9c  bts     dword ptr [rbx+4], 0Ah
0x180003ca1  mov     rbx, [rsp+28h+arg_0]
0x180003ca6  add     rsp, 20h
0x180003caa  pop     rdi
0x180003cab  retn
```
