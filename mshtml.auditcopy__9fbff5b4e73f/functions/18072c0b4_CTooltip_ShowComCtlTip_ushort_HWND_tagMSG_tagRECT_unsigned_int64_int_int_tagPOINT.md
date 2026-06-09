# CTooltip::ShowComCtlTip(ushort *,HWND__ *,tagMSG *,tagRECT *,unsigned __int64,int,int,tagPOINT *)

- ea: `0x18072c0b4`
- end: `0x18072c472`
- name: `?ShowComCtlTip@CTooltip@@AEAAJPEAGPEAUHWND__@@PEAUtagMSG@@PEAUtagRECT@@_KHHPEAUtagPOINT@@@Z`
- size: `958`
- prototype: `__int64 __fastcall(CTooltip *this, char *, HWND, struct tagMSG *, RECT *lprc1, unsigned __int64, int, int, struct tagPOINT *lpPoints)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1807235f8`

## callees

- `0x18005cccc`
- `0x18072c0b4`
- `0x180b616dc`
- `0x180b618fc`
- `0x180b6a470`
- `0x1810f6516`

## import_xrefs

- `USER32!IsWindow` at `0x18072c0f6`
- `USER32!IsWindow` at `0x18072c0f6`
- `USER32!DestroyWindow` at `0x18072c109`
- `USER32!DestroyWindow` at `0x18072c109`
- `USER32!SendMessageW` at `0x18072c17b`
- `USER32!SendMessageW` at `0x18072c215`
- `USER32!SendMessageW` at `0x18072c256`
- `USER32!SendMessageW` at `0x18072c315`
- `USER32!SendMessageW` at `0x18072c330`
- `USER32!SendMessageW` at `0x18072c40e`
- `USER32!SendMessageW` at `0x18072c44f`
- `USER32!SendMessageW` at `0x18072c17b`
- `USER32!SendMessageW` at `0x18072c215`
- `USER32!SendMessageW` at `0x18072c256`
- `USER32!SendMessageW` at `0x18072c315`
- `USER32!SendMessageW` at `0x18072c330`
- `USER32!SendMessageW` at `0x18072c40e`
- `USER32!SendMessageW` at `0x18072c44f`
- `USER32!MapWindowPoints` at `0x18072c428`
- `USER32!MapWindowPoints` at `0x18072c428`
- `USER32!EqualRect` at `0x18072c1f2`
- `USER32!EqualRect` at `0x18072c3c1`
- `USER32!EqualRect` at `0x18072c1f2`
- `USER32!EqualRect` at `0x18072c3c1`

## pseudocode

```c

```
